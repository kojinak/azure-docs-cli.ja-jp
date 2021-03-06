---
title: Azure CLI で使用可能な拡張機能
description: Azure CLI で公式にサポートされている拡張機能の完全な一覧です。
author: sptramer
ms.author: sttramer
manager: carmonm
ms.date: 04/17/2019
ms.topic: article
ms.prod: azure
ms.technology: azure-cli
ms.devlang: azure-cli
ms.openlocfilehash: bfcd0bb57e60e698e3ac7e6edeb64d52e9eb1341
ms.sourcegitcommit: 334a1da92a73e42e715e33470057f4194f10b2ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59724610"
---
# <a name="available-extensions-for-the-azure-cli"></a>Azure CLI で使用可能な拡張機能

この記事では、Microsoft によってサポートされている、Azure CLI で使用可能な拡張機能の完全な一覧を示します。

拡張機能の一覧は、CLI から入手することもできます。 取得するには、[az extension list-available](/cli/azure/extension?view=azure-cli-latest#az-extension-list-available) を実行します。

```azurecli-interactive
az extension list-available --output table
```

| Name | バージョン | まとめ | プレビュー |
|------|---------|---------|---------|
| [aem](https://github.com/Azure/azure-cli-extensions) | 0.1.1 | Azure Enhanced Monitoring Extension for SAP を管理します |  |
| [aks-preview](https://github.com/Azure/azure-cli-extensions/tree/master/src/aks-preview) | 0.3.1 | 次期 AKS 機能のプレビューを提供します | はい |
| [alias](https://github.com/Azure/azure-cli-extensions) | 0.5.2 | コマンドのエイリアスをサポートします | はい |
| [anf-preview](https://github.com/Azure/azure-cli-extensions/tree/master/src/anf-preview) | 0.1.0 | 次期 Azure NetApp Files (ANF) 機能のプレビューを提供します。 | はい |
| [appconfig](https://github.com/Azure/azure-cli-extensions) | 0.4.0 | 次期アプリ構成機能のプレビューを提供します。 | はい |
| [application-insights](https://github.com/Azure/azure-cli-extensions/tree/master/src/application-insights) | 0.1.1 | Application Insights コンポーネントの管理と、それらのコンポーネントのメトリック、イベント、およびログのクエリをサポートします。 | はい |
| [azure-batch-cli-extensions](https://github.com/Azure/azure-batch-cli-extensions) | 3.0.3 | Azure Batch サービスを操作するための追加コマンド |  |
| [azure-cli-iot-ext](https://github.com/azure/azure-iot-cli-extension) | 0.7.0 | Azure IoT Hub、IoT Edge、および IoT Device Provisioning Service にデータ プレーン コマンド レイヤーを提供します |  |
| [azure-devops](https://github.com/Microsoft/azure-devops-cli-extension) | 0.4.0 | Azure DevOps を管理するためのツールです。 | はい |
| [azure-firewall](https://github.com/Azure/azure-cli-extensions/tree/master/src/azure-firewall) | 0.1.2 | Azure Firewall のリソースを管理します。 | はい |
| [botservice](https://github.com/Azure/azure-cli-extensions) | 0.4.3 | ネイティブの Bot Service CLI コマンド モジュールの問題のバグ修正。 | はい |
| [db-up](https://github.com/Azure/azure-cli-extensions/tree/master/src/db-up) | 0.1.11 | Azure データベースのワークフローを簡略化するための、その他のコマンド。 | はい |
| [dev-spaces](https://github.com/Azure/azure-cli-extensions) | 1.0.0 | Dev Spaces は、高速で反復的な Kubernetes 開発エクスペリエンスをチームに提供します。 |  |
| [dms-preview](https://github.com/Azure/azure-cli-extensions/tree/master/src/dms-preview) | 0.8.0 | 新しい Database Migration Service のシナリオをサポートします。 | はい |
| [dns](https://github.com/Azure/azure-cli-extensions) | 0.0.2 | DNS ゾーン向けの Azure CLI 拡張機能 |  |
| [eventgrid](https://github.com/Azure/azure-cli-extensions) | 0.4.1 | Microsoft Azure コマンド ライン ツールの EventGrid コマンド モジュールです。 | はい |
| [express-route](https://github.com/Azure/azure-cli-extensions/tree/master/src/express-route) | 0.1.3 | ExpressRoute プレビュー機能を管理します。 | はい |
| [express-route-cross-connection](https://github.com/Azure/azure-cli-extensions/tree/master/src/express-route-cross-connection) | 0.1.1 | ExpressRoute のクロス接続を使用して、顧客の ExpressRoute 回線を管理します。 |  |
| [find](https://github.com/Azure/azure-cli-extensions/tree/master/src/find) | 0.3.0 | CLI 情報に対するインテリジェントな照会。 | はい |
| [front-door](https://github.com/Azure/azure-cli-extensions/tree/master/src/front-door) | 0.1.5 | ネットワークの Front Door を管理します。 | はい |
| [image-copy-extension](https://github.com/Azure/azure-cli-extensions) | 0.0.9 | リージョン間での管理対象 VM イメージのコピーをサポートします |  |
| [interactive](https://github.com/Azure/azure-cli) | 0.4.2 | Microsoft Azure コマンド ライン対話型シェル | はい |
| [keyvault-preview](https://github.com/Azure/azure-keyvault-cli-extension) | 0.1.3 | Azure Key Vault のコマンドをプレビューします。 | はい |
| [log-analytics](https://github.com/Azure/azure-cli-extensions/tree/master/src/log-analytics) | 0.1.3 | Azure Log Analytics のクエリ機能をサポートします。 | はい |
| [managementgroups](https://github.com/Azure/azure-cli-extensions) | 0.1.0 | 管理グループ向け Azure CLI 拡張機能 |  |
| [managementpartner](https://github.com/Azure/azure-cli-extensions) | 0.1.2 | 管理パートナーのプレビューをサポートします |  |
| [mesh](https://github.com/Azure/azure-cli-extensions) | 0.10.4 | Microsoft Azure Service Fabric Mesh のサポート - パブリック プレビュー | はい |
| [mixed-reality](https://github.com/Azure/azure-cli-extensions) | 0.0.1 | Mixed Reality Azure CLI 拡張機能。 |  |
| [privatedns](https://github.com/Azure/azure-cli-extensions) | 0.1.0 | プライベート DNS ゾーンを管理するためのコマンド | はい |
| [rdbms-vnet](https://github.com/Azure/azure-cli-extensions) | 10.0.0 | Azure MySQL および Azure PostgreSQL のリソースで仮想ネットワーク ルールをサポートします |  |
| [resource-graph](https://github.com/Azure/azure-cli-extensions/tree/master/src/resource-graph) | 0.1.8 | Resource Graph を使用した Azure リソースのクエリをサポートします。 | はい |
| [sap-hana](https://github.com/Azure/azure-hanaonazure-cli-extension) | 0.3.4 | SAP HanaOnAzure インスタンスを操作するための追加コマンド。 |  |
| [signalr](https://github.com/Azure/azure-cli-extensions) | 0.1.0 | SignalR 管理プレビューをサポートします。 | はい |
| [sqlvm-preview](https://github.com/Azure/azure-cli-extensions/tree/master/src/sqlvm-preview) | 0.1.0 | SQL 仮想マシン、グループ、および可用性グループ リスナーを管理するためのツールです。 | はい |
| [storage-preview](https://github.com/Azure/azure-cli-extensions/tree/master/src/storage-preview) | 0.2.4 | 次期ストレージ機能のプレビューを提供します。 | はい |
| [サブスクリプション](https://github.com/Azure/azure-cli-extensions) | 0.1.1 | サブスクリプション管理プレビューをサポートします。 |  |
| [virtual-network-tap](https://github.com/Azure/azure-cli-extensions/tree/master/src/virtual-network-tap) | 0.1.0 | 仮想ネットワーク タップ (VTAP) を管理します。 | はい |
| [virtual-wan](https://github.com/Azure/azure-cli-extensions/tree/master/src/virtual-wan) | 0.1.0 | 仮想 WAN、ハブ、VPN ゲートウェイ、および VPN サイトを管理します。 | はい |
| [webapp](https://github.com/Azure/azure-cli-extensions) | 0.2.16 | Azure App Service のその他のコマンド。 | はい |