---
lab:
  title: モデルを解釈する
ms.openlocfilehash: 67c49bac773fe3da774f583729a0f9a9de1b3b44
ms.sourcegitcommit: 18f734eeb1031a9cb69c3b294632efd2e69324ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "137894468"
---
# <a name="interpret-models"></a>モデルを解釈する

機械学習は、健康、安全性、経済的繁栄など、人々の生活のさまざまな側面に影響を与える意思決定にますます不可欠になっているため、モデルでどのように予測が行われるかを理解し、機械学習に基づく意思決定の根拠について説明できるようにすることが重要です。

## <a name="before-you-start"></a>開始する前に

まだ行っていない場合は、" *[Azure Machine Learning ワークスペースを作成する](01-create-a-workspace.md)* " 演習を完了して、Azure Machine Learning ワークスペースとコンピューティング インスタンスを作成し、この演習に必要なノートブックのクローンを作成してください。

## <a name="open-jupyter"></a>Jupyter を開く

Azure Machine Learning スタジオの **[ノートブック]** ページを使用してノートブックを実行することもできますが、*Jupyter* のような、より完全な機能を備えたノートブック開発環境を使用する方が生産性が高いことが多くあります。

1. [Azure Machine Learning スタジオ](https://ml.azure.com) で、ワークスペースの **[コンピューティング]** ページを表示し、 **[コンピューティング インスタンス]** タブで、まだ実行されていないコンピューティング インスタンスを起動します。
2. コンピューティング インスタンスの実行時に、**Jupyter** リンクをクリックして、新しいブラウザー タブで Jupyter のホーム ページを開きます。

## <a name="use-the-sdk-to-interpret-models"></a>SDK を使用してモデルを解釈する

この演習では、モデルを解釈するためのコードをノートブックで提供します。

1. Jupyter ホーム ページで、ノートブック リポジトリを複製した **/users/*your-user-name*/mslearn-dp100** フォルダーを参照し、**モデルを解釈する** ノートブックを開きます。
2. 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。
3. ノートブック内のコードの実行が終了したら、 **[ファイル]** メニューの **[閉じて停止]** をクリックして閉じ、Python カーネルをシャットダウンします。 その後、すべての Jupyter ブラウザー タブを閉じます。

## <a name="clean-up"></a>クリーンアップ

Azure Machine Learning での作業が終わったら、Azure Machine Learning スタジオの **[コンピューティング]** ページで、 **[コンピューティング インスタンス]** タブを選択し、 **[停止]** をクリックしてシャットダウンします。 それ以外の場合は、次のラボのために実行したままにします。

> **注**:コンピューティングを停止すると、サブスクリプションがコンピューティング リソースに対して課金されなくなります。 ただし、サブスクリプションに Azure Machine Learning ワークスペースが存在する限り、データ ストレージに対して少額が課金されます。 Azure Machine Learning の探索を完了したら、Azure Machine Learning ワークスペースとそれに関連付けられたリソースを削除できます。 ただし、このシリーズの他のラボを修了する場合は、" *[Azure Machine Learning ワークスペースを作成する](01-create-a-workspace.md)* " 演習を繰り返して、ワークスペースを作成し、環境を準備する必要があります。