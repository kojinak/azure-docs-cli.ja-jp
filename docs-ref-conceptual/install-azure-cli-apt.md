---
title: apt を使用して Linux に Azure CLI をインストールする
description: apt パッケージ マネージャーで Azure CLI をインストールする方法
author: sptramer
ms.author: sttramer
manager: carmonm
ms.date: 03/19/2019
ms.topic: conceptual
ms.prod: azure
ms.technology: azure-cli
ms.devlang: azurecli
ms.openlocfilehash: fa2e1db439b4836d7506409b3abcce74fb6e6695
ms.sourcegitcommit: 5864f72b9a6fbf82a4d98bf805b3a16a7da18556
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2019
ms.locfileid: "58343147"
---
# <a name="install-azure-cli-with-apt"></a>apt での Azure CLI のインストール

Ubuntu や Debian など、`apt` が付属するディストリビューションを実行している場合は、Azure CLI 用に x86_64 パッケージを使用できます。 このパッケージは、以下でテストされています。

* Ubuntu trusty、xenial、artful、および bionic
* Debian wheezy、jessie、および stretch

[!INCLUDE [current-version](includes/current-version.md)]

> [!NOTE]
>
> Azure CLI のパッケージによって独自の Python インタープリターがインストールされ、システム上の Python は使用されません。

## <a name="install"></a>Install

1. インストール プロセスに必要なパッケージを取得します。

    ```bash
    sudo apt-get update
    sudo apt-get install curl apt-transport-https lsb-release gpg
    ```

2. Microsoft の署名キーをダウンロードしてインストールします。

    ```bash
    curl -sL https://packages.microsoft.com/keys/microsoft.asc | \
        gpg --dearmor | \
        sudo tee /etc/apt/trusted.gpg.d/microsoft.asc.gpg > /dev/null
    ```

3. <div id="set-release"/>Azure CLI  ソフトウェア リポジトリを追加します。

    ```bash
    AZ_REPO=$(lsb_release -cs)
    echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | \
        sudo tee /etc/apt/sources.list.d/azure-cli.list
    ```

4. リポジトリ情報を更新し、`azure-cli` パッケージをインストールします。

    ```bash
    sudo apt-get update
    sudo apt-get install azure-cli
    ```

`az` コマンドで Azure CLI を実行します。 サインインするには、[az login](/cli/azure/reference-index#az-login) コマンドを使用します。

[!INCLUDE [interactive-login](includes/interactive-login.md)]

さまざまな認証方法の詳細については、「[Azure CLI を使用してサインインする](authenticate-azure-cli.md)」を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

ここでは、`apt` でのインストール時に発生する一般的な問題をいくつか示します。 ここで取り上げていない問題が発生した場合は、[GitHub で問題を報告](https://github.com/Azure/azure-cli/issues)してください。

### <a name="lsbrelease-does-not-return-the-correct-base-distribution-version"></a>lsb_release がベース ディストリビューション バージョンを返さない

Linux Mint など、Ubuntu や Debian から派生する一部のディストリビューションでは、正しいバージョン名が `lsb_release` から返されない場合があります。 この値は、インストール プロセスで、インストールするパッケージを特定するときに使用されます。 ディストリビューションの派生元である Ubuntu バージョンまたは Debian バージョンのコード名がわかっている場合は、[リポジトリを追加する](#set-release)ときに `AZ_REPO` 値を手動で設定できます。 それ以外の場合は、ご自身のディストリビューションについて、ベース ディストリビューションのコード名を調べて、`AZ_REPO` を正しい値に設定する方法をご確認ください。

### <a name="no-package-for-your-distribution"></a>ご使用のディストリビューションのパッケージがない

ディストリビューションがリリースされてから、そのディストリビューション用の Azure CLI パッケージが利用可能になるまではしばらくかかることがあります。 Azure CLI は、以降のバージョンの依存関係に関して弾力性を持つように、また可能な限り以降のバージョンに依存しないように設計されています。 ベース ディストリビューションに使用できるパッケージがない場合は、以前のディストリビューション用のパッケージをお試しください。

これを行うには、[リポジトリを追加する](#set-release)ときに `AZ_REPO` の値を手動で設定します。 Ubuntu ディストリビューションには `bionic` リポジトリーを使用し、Debian ディストリビューションには `stretch` を使用します。 Ubuntu Trusty および Debian Wheezy より前にリリースされたディストリビューションはサポートされていません。

[!INCLUDE[troubleshoot-wsl.md](includes/troubleshoot-wsl.md)]

## <a name="update"></a>アップデート

CLI パッケージを更新するには、`apt-get upgrade` を使用します。

   ```bash
   sudo apt-get update && sudo apt-get upgrade
   ```

> [!NOTE]
> このコマンドにより、システムにインストールされている、依存関係が変更されていないすべてのパッケージがアップグレードされます。
> CLI だけをアップグレードするには、`apt-get install` を使用します。
> 
> ```bash
> sudo apt-get update && sudo apt-get install --only-upgrade -y azure-cli
> ```

## <a name="uninstall"></a>アンインストール

[!INCLUDE [uninstall-boilerplate.md](includes/uninstall-boilerplate.md)]

1. `apt-get remove` を使用してアンインストールします。

    ```bash
    sudo apt-get remove -y azure-cli
    ```

2. CLI を再インストールする予定がない場合は、Azure CLI リポジトリ情報を削除します。

   ```bash
   sudo rm /etc/apt/sources.list.d/azure-cli.list
   ```

3. 署名キーを削除します。

    ```bash
    sudo rm /etc/apt/trusted.gpg.d/microsoft.asc.gpg
    ```

4. 不要なパッケージを削除します。

   ```bash
   sudo apt autoremove
   ```

## <a name="next-steps"></a>次の手順

これで Azure CLI をインストールできました。次は、その機能と一般的なコマンドを簡単に見ていきましょう。

> [!div class="nextstepaction"]
> [Azure CLI の概要](get-started-with-azure-cli.md)
