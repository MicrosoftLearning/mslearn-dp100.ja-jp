---
lab:
  title: 差分プライバシーを探索する
ms.openlocfilehash: b0c369d3c6405fa3990596a738962115e6889ec2
ms.sourcegitcommit: 18f734eeb1031a9cb69c3b294632efd2e69324ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "137894505"
---
# <a name="explore-differential-privacy"></a>差分プライバシーを説明する

多くの場合、機械学習モデルをトレーニングするために使用されるデータには、非公開にすべきセンシティブな値が含まれています。 差分プライバシーとは、統計的な測定値や集計値が元の生データと一貫性を保つようにデータに "ノイズ" を追加する手法ですが、個々の観測値を特定することはより困難です。

## <a name="before-you-start"></a>開始する前に

まだ行っていない場合は、" *[Azure Machine Learning ワークスペースを作成する](01-create-a-workspace.md)* " 演習を完了して、Azure Machine Learning ワークスペースとコンピューティング インスタンスを作成し、この演習に必要なノートブックのクローンを作成してください。

## <a name="open-jupyter"></a>Jupyter を開く

Azure Machine Learning スタジオの **[ノートブック]** ページを使用してノートブックを実行することもできますが、*Jupyter* のような、より完全な機能を備えたノートブック開発環境を使用する方が生産性が高いことが多くあります。

1. [Azure Machine Learning スタジオ](https://ml.azure.com) で、ワークスペースの **[コンピューティング]** ページを表示し、 **[コンピューティング インスタンス]** タブで、まだ実行されていないコンピューティング インスタンスを起動します。
2. コンピューティング インスタンスの実行時に、**Jupyter** リンクをクリックして、新しいブラウザー タブで Jupyter のホーム ページを開きます。

## <a name="use-smartnoise-to-explore-differential-privacy"></a>SmartNoise を使用して差分プライバシーを説明する

この演習では、SmartNoise を使用して差分プライバシーを説明するためのコードをノートブックで提供します。

1. Jupyter ホーム ページで、ノートブック リポジトリを複製した **/users/*your-user-name*/mslearn-dp100** フォルダーを参照し、**差分プライバシーを説明する** ノートブックを開きます。
2. 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。
3. ノートブック内のコードの実行が終了したら、 **[ファイル]** メニューの **[閉じて停止]** をクリックして閉じ、Python カーネルをシャットダウンします。 その後、すべての Jupyter ブラウザー タブを閉じます。

## <a name="clean-up"></a>クリーンアップ

Azure Machine Learning での作業が終わったら、Azure Machine Learning スタジオの **[コンピューティング]** ページで、 **[コンピューティング インスタンス]** タブを選択し、 **[停止]** をクリックしてシャットダウンします。 それ以外の場合は、次のラボのために実行したままにします。

> **注**:コンピューティングを停止すると、サブスクリプションがコンピューティング リソースに対して課金されなくなります。 ただし、サブスクリプションに Azure Machine Learning ワークスペースが存在する限り、データ ストレージに対して少額が課金されます。 Azure Machine Learning の探索を完了したら、Azure Machine Learning ワークスペースとそれに関連付けられたリソースを削除できます。 ただし、このシリーズの他のラボを修了する場合は、" *[Azure Machine Learning ワークスペースを作成する](01-create-a-workspace.md)* " 演習を繰り返して、ワークスペースを作成し、環境を準備する必要があります。