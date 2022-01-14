---
title: オンライン ホステッド インストラクション
permalink: index.html
layout: home
---

# Azure Machine Learning 演習

このリポジトリには、Microsoft のコース [DP-100 *Designing and Implementing a Data Science Solution on Azure*](https://docs.microsoft.com/learn/certifications/courses/dp-100t01) の実践的な演習と、同等の [Microsoft Learn のマイペースで進められるモジュール](https://docs.microsoft.com/learn/paths/build-ai-solutions-with-azure-ml-service/) が含まれています。この演習は、学習教材に付属しており、説明されている技術を使用して練習できるようになっています。

この演習を完了するには、Microsoft Azure サブスクリプションが必要です。講師がサブスクリプションを提供していない場合は、[https://azure.microsoft.com](https://azure.microsoft.com) で無料試用版にサインアップできます。

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| 演習 |
| ------- | 
{% for activity in labs  %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
