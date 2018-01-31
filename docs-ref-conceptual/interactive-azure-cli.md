---
title: "Azure CLI 2.0 対話モード"
description: "対話モードで Azure CLI 2.0 を使用します。"
keywords: "Azure CLI 2.0, 対話モード"
author: rloutlaw
ms.author: routlaw
manager: douge
ms.date: 04/06/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: azurecli
ms.service: multiple
ms.assetid: 
ms.openlocfilehash: fb260d7385728acd0c699488ecb5b108afefd08c
ms.sourcegitcommit: 2e4d0bdd94c626e061434883032367b5619de4fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2017
---
# <a name="interactive-azure-cli-20"></a>対話型 Azure CLI 2.0

Azure CLI 2.0 を対話モードで使用するには、`az interactive` コマンドを実行します。
これにより対話型シェルに移動します。このシェルでは、コマンドがオートコンプリート入力されるほか、コマンドやそのパラメーターの説明、およびコマンドの例にアクセスできます。

![対話モード](./media/interactive-azure-cli/webapp-create.png)

> [!NOTE]
> 黒の背景でも読みやすさは変わらないため、ここでは既定のスタイルを使用していません。

まだアカウントにログインしていない場合は、`login` コマンドを使用してログインします。

## <a name="configure"></a>構成

対話モードでは、必要に応じて、コマンドの説明、パラメーターの説明、およびコマンドの例が表示されます。
説明と例のオン/オフを切り替えるには、`F1` を使用します。

![説明と例](./media/interactive-azure-cli/descriptions-and-examples.png)

パラメーターの既定値の表示のオン/オフを切り替えるには、`F2` を使用します。

![既定値](./media/interactive-azure-cli/defaults.png)

`F3` では、一部のキー ジェスチャの表示を切り替えることができます。

![ジェスチャ](./media/interactive-azure-cli/gestures.png)

## <a name="scope"></a>Scope

対話モードのスコープを、`vm`、`vm image` などの特定のコマンド グループに指定することができます。
これを行うと、すべてのコマンドがそのスコープ内で解釈されます。
そのコマンド グループですべての作業を行う場合は、これを使って簡略化できます。

次のコマンドを入力する代わりに、

```azurecli
az>> vm create -n myVM -g myRG --image UbuntuLTS
az>> vm list -o table
```

次のように、vm コマンド グループにスコープを指定して、対象のコマンドを入力します。

```azurecli
az>> %%vm
az vm>> create -n myVM -g myRG --image UbuntuLTS
az vm>>list -o table
```

下位レベルのコマンド グループにもスコープを指定できます。
`vm image` にスコープを指定するには、`%%vm image` を使用します。
この場合、既に `vm` にスコープを指定しているため、`%%image` を使用します。

```azurecli
az vm>> %%image
az vm image>>
```

この時点で、`%%..` を使用すると、スコープを `vm` に戻すことができます。また、`%%` だけを指定すると、スコープをルートに指定できます。

```azurecli
az vm image>> %%
az>>
```

## <a name="query"></a>クエリ

最後に実行したコマンドの結果に対して、JMESPath クエリを実行することができます。
たとえば、VM を作成した後、その VM が完全にプロビジョニングされていることを確認できます。

```azurecli
az>> vm create --name myVM --resource-group myRG --image UbuntuLTS --no-wait
az>> ? [*].provisioningState
```

```
[
  "Creating"
]
```

コマンドの結果に対してクエリを実行する方法の詳細については、[Azure 2.0 でのコマンド結果に対するクエリの実行](query-azure-cli.md)に関するページをご覧ください。

## <a name="bash-commands"></a>Bash コマンド

`#[cmd]` を使用して、対話モードのままシェル コマンドを実行できます。

```azurecli
az>> #dir
```

## <a name="examples"></a>例

一部のコマンドには例が多数あります。
次の例のページにスクロールするには、`CTRL-N` を使用します。前のページに戻るには、`CTRL-Y` を使用します。

![例](./media/interactive-azure-cli/examples.png)

`::#` を使用して、特定の例を確認することもできます。

```azurecli
az>> vm create ::8
```