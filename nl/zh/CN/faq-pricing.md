---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-10"

subcollection: speech-to-text

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# 定价常见问题
{: #faq-pricing}

1.  <span style="color:#003F69">使用 {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.speechtotextshort}} 标准服务的价格是多少？</span>

    {{site.data.keyword.speechtotextshort}} 服务的定价为每分钟 0.02 美元 (USD)。此价格适用于使用宽带和窄带模型。有关更多信息，请参阅 {{site.data.keyword.speechtotextshort}} [服务登录页面 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/watson/developercloud/speech-to-text.html#pricing-block){: new_window}。

1.  <span style="color:#003F69">“按分钟定价”是什么意思？是按发送到服务的音频的分钟数收费，还是按服务处理音频所花费的分钟数收费？</span>

    价格会按发送到服务的音频量计算，而不是按服务处理音频所花费的时间计算。

1.  <span style="color:#003F69">是否会将每个 API 调用的音频长度都四舍五入到最接近的分钟数？例如，如果我发送了两个音频文件，每个文件的长度都是 30 秒，那么是按 2 分钟还是 1 分钟收费？</span>

    {{site.data.keyword.IBM_notm}} 不会对服务收到的每个 API 调用的音频长度进行四舍五入。{{site.data.keyword.IBM_notm}} 会在月末汇总该月的所有使用量，并四舍五入到最接近的分钟数。在此示例中，如果您发送了两个长度为 30 秒的音频文件，那么 {{site.data.keyword.IBM_notm}} 会将音频的总持续时间合计为 1 分钟，并收取 0.02 美元 (USD) 的费用。

1.  <span id="graduated" style="color:#003F69">基于用量的累进分层定价如何计费？</span>

    分层定价模型旨在为继续使用服务的高用量用户提供进一步的折扣。在达到每月音频总量的特定阈值后，额外的音频分钟数将享受更低的每分钟定价。有关更多信息，请参阅服务的[定价页面 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/catalog/services/speech-to-text){: new_window}。

1.  <span style="color:#003F69">如果我使用服务在一个月内转录了 27.5 万分钟的音频，那么按分层定价的话总费用会是多少？</span>

    -   对于前 25 万分钟的音频，将按每分钟 0.02 美元 (USD) 收费，即 250,000 * 0.02 美元 = 5000.00 美元 (USD)。
    -   对于剩余 2.5 万分钟的音频，将按更低的费率（每分钟 0.015 美元 (USD)）收费，即 25,000 * 0.015 美元 = 375.00 美元 (USD)。
    -   在这种情况下，该月的总费用为 5375.00 美元 (USD)。

1.  <span style="color:#003F69">使用服务的定制接口的价格是多少？创建和存储定制模型是否收费？</span>

    对于*语言模型定制*，{{site.data.keyword.IBM_notm}} 不会对创建或托管定制语言模型进行收费，而仅会对将模型用于识别请求进行收费。使用定制语言模型进行转录时，每分钟会产生 0.03 美元 (USD) 的附加费用。此费用是在每分钟 0.02 美元 (USD) 的标准使用量费用之上额外收取的。这适用于定制接口支持的所有语言。因此，使用定制语言模型进行语音识别的总费用为每分钟 0.05 美元 (USD)。

    对于*声学模型定制*（适用于所有受支持语言的 Beta 接口），{{site.data.keyword.IBM_notm}} 不会对创建或托管定制声学模型，以及使用定制声学模型识别语音进行收费。将定制声学模型用于识别请求在将来可能会收费。
