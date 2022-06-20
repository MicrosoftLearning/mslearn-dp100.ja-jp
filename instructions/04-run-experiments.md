---
lab:
  title: 実験の実行
ms.openlocfilehash: 62b6b79c99142d4311c2d9c0db4b02cfd710feb6
ms.sourcegitcommit: 66d8872bc3d24c2121e225be132b56f4df7920ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "138597275"
---
# <a name="run-experiments"></a>実験を実行する

実験はデータ サイエンティストの研究の中核です。 Azure Machine Learning では、*実験* を使用してスクリプトまたはパイプラインを実行し、通常は出力を生成し、メトリックを記録します。 この演習では、Azure Machine Learning SDK を使用して Python コードを実験として実行します。

## <a name="before-you-start"></a>開始する前に

まだ行っていない場合は、" *[Azure Machine Learning ワークスペースを作成する](01-create-a-workspace.md)* " 演習を完了して、Azure Machine Learning ワークスペースとコンピューティング インスタンスを作成し、この演習に必要なノートブックのクローンを作成してください。

## <a name="open-jupyter"></a>Jupyter を開く

Azure Machine Learning スタジオの **[ノートブック]** ページを使用してノートブックを実行することもできますが、*Jupyter* のような、より完全な機能を備えたノートブック開発環境を使用する方が生産性が高いことが多くあります。 幸いなことに、Azure Machine Learning のコンピューティング インスタンスには Jupyter がインストールされています。

> **ヒント**: Jupyter Notebook はデータ サイエンスのための一般的に使用されているオープン ソース ツールです。 詳しくない場合は、[ドキュメント](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html)を参照してください。

1. [Azure Machine Learning スタジオ](https://ml.azure.com) で、ワークスペースの **[コンピューティング]** ページを表示し、 **[コンピューティング インスタンス]** タブで、まだ実行されていないコンピューティング インスタンスを起動します。
2. コンピューティング インスタンスの実行時に、**Jupyter** リンクをクリックして、新しいブラウザー タブで Jupyter のホーム ページを開きます。必ず *JupyterLab* ではなく *Jupyter* を開いてください。

> **ヒント**: Python 初心者の場合は、 [Python チート シート](cheat-sheets/dp100-cheat-sheet-python.pdf)を参照すると、コードについて理解できます。

## <a name="verify-the-azure-machine-learning-sdk-is-installed"></a>Azure Machine Learning SDK がインストールされていることを確認する

Azure Machine Learning SDK は、コンピューティング インスタンスにデフォルトでインストールされています。 次の手順に従ってインストールを確認します。

1. Jupyter Notebook 環境で、新しい **ターミナル** を作成します。 これにより、コマンド シェルを含む新しいタブが開きます。
2. 次のコマンドを入力して、Azure MLSDK がインストールされていることを確認します。

    ```bash
    pip show azureml-sdk
    ```

    インストールされている SDK パッケージのバージョンを書き留めます。

3. **azureml-sdk** SDK パッケージは、Azure Machine Learning を使用するために必要な最も重要なライブラリを提供しています>しかし、メインの SDK パッケージに含まれていない他の有用なライブラリを含むいくつかの追加パッケージがあります。 次のコマンドを使用して、Azure Machine Learning の情報をノートブックに表示するためのライブラリを含む **azureml-widgets** パッケージもインストールされていることを確認します。

    ```bash
    pip show azureml-widgets
    ```

4. **[ターミナル]** タブを閉じ、Jupyter ホーム ページを含むタブに戻ります。

> **詳細情報**: Azure ML SDK とそのオプション コンポーネントのインストールの詳細については、[Azure ML SDK ドキュメント](https://docs.microsoft.com/python/api/overview/azure/ml/install?view=azure-ml-py)を参照してください。

## <a name="run-experiments-in-a-notebook"></a>ノートブックで実験を実行する

Azure Machine Learning での実験は、ある種の *制御* 層 (多くの場合はスクリプトまたはプログラム) から開始する必要があります。 この演習では、ノートブックを使用して実験を制御します。

1. Jupyter ホーム ページで、ノートブック リポジトリを複製した **/users/*your-user-name*/mslearn-dp100** フォルダーを参照し、**Run Experiments (実験の実行)** ノートブックを開きます。
2. 次に、ノートブック内の注意事項を読み、各コード セルを順番に実行します。
3. ノートブック内のコードの実行が終了したら、 **[ファイル]** メニューの **[閉じて停止]** をクリックして閉じ、Python カーネルをシャットダウンします。 その後、すべての Jupyter ブラウザー タブを閉じます。

## <a name="clean-up"></a>クリーンアップ

Azure Machine Learning での作業が終わったら、Azure Machine Learning スタジオの **[コンピューティング]** ページで、 **[コンピューティング インスタンス]** タブを選択し、 **[停止]** をクリックしてシャットダウンします。 それ以外の場合は、次のラボのために実行したままにします。

> **注**:コンピューティングを停止すると、サブスクリプションがコンピューティング リソースに対して課金されなくなります。 ただし、サブスクリプションに Azure Machine Learning ワークスペースが存在する限り、データ ストレージに対して少額が課金されます。 Azure Machine Learning の探索を完了したら、Azure Machine Learning ワークスペースとそれに関連付けられたリソースを削除できます。 ただし、このシリーズの他のラボを修了する場合は、" *[Azure Machine Learning ワークスペースを作成する](01-create-a-workspace.md)* " 演習を繰り返して、ワークスペースを作成し、環境を準備する必要があります。