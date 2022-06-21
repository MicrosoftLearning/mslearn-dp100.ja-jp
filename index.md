---
title: オンライン ホステッド インストラクション
permalink: index.html
layout: home
ms.openlocfilehash: a2eb157b1d188655f4cfbcc575befec4a2e9c623
ms.sourcegitcommit: 18f734eeb1031a9cb69c3b294632efd2e69324ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "137894578"
---
# <a name="azure-machine-learning-exercises"></a>Azure Machine Learning 演習

このリポジトリには、Microsoft の「コース [DP-100 "*Azure でのデータ サイエンス ソリューションの設計と実装*"](https://docs.microsoft.com/learn/certifications/courses/dp-100t01)」の実践的な演習と、同等の [Microsoft Learn のマイペースで進められるモジュール](https://docs.microsoft.com/learn/paths/build-ai-solutions-with-azure-ml-service/)が含まれています。 演習は学習教材に沿って設計されており、教材で説明されているテクノロジを使って学習できます。

この演習を完了するには、Microsoft Azure サブスクリプションが必要です。 講師からサブスクリプションが提供されていない場合は、[https://azure.microsoft.com](https://azure.microsoft.com) で無料の試用版にサインアップできます。

{% assign labs = site.pages | where_exp:"page", "page.url contains '/instructions'" %}
| 演習 |
| ------- | 
{% for activity in labs %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
