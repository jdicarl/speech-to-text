---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-03"

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

# 製品について
{: #about}

**サービス更新:** *{{site.data.keyword.speechtotextshort}} サービスは、2019 年 4 月 3 日に更新されました。このサービスでは、1 つのカスタム音響モデルに最大 200 時間の音声を追加できるようになりました。詳しくは、[2019 年 4 月 3 日のサービス更新](/docs/services/speech-to-text/release-notes.html#April2019)を参照してください*。

{{site.data.keyword.speechtotextfull}} サービスは、さまざまな用途に使用できる音声書き起こし機能を提供します。このサービスは機械学習を活用して、文法、言語構造、および音声シグナルの構成に関する知識を組み合わせることで、人間の音声を正確に書き起こします。このサービスは繰り返し更新されて、受け取る音声データが増えるほど書き起こし機能が向上します。
{: shortdesc}

このサービスは各種のインターフェースを提供しているため、音声を入力して書き起こしテキストを出力するどのような用途にも対応できます。例えば、次のような用途に使用できます。

-   アプリケーション、埋め込みデバイス、および車両装備品の音声制御
-   会議や電話会議の書き起こし
-   E メール・メッセージやメモの口述筆記

## サポートされているインターフェース
{: #interfaces}

{{site.data.keyword.speechtotextshort}} サービスでは、音声認識用に次の 3 種類のインターフェースが提供されています。

-   [WebSocket インターフェース](/docs/services/speech-to-text/websockets.html)では、永続的な低遅延の全二重接続をサービスとの間で確立できます。単一の要求で最大 100 MB の音声データをサービスに渡すことができます。
-   [同期 HTTP インターフェース](/docs/services/speech-to-text/http.html)では、サービスに対して基本的な HTTP 呼び出しを発行できます。単一の要求で最大 100 MB の音声データを渡すことができます。
-   [非同期 HTTP インターフェース](/docs/services/speech-to-text/async.html)では、サービスに対して非ブロッキング呼び出しを発行できます。単一の要求で最大 1 GB の音声データを渡すことができます。

このサービスでさらに提供されている[カスタマイズ・インターフェース](/docs/services/speech-to-text/custom.html)を使用して、対象の言語や音響上の要件に合わせて音声認識を調整できます。分野固有の用語を追加してモデルの語彙を拡張することも、モデルをカスタマイズして対象の音声の音響特性に適合させることもできます。[文法](/docs/services/speech-to-text/grammar.html)を追加することで、サービスで認識できる句を制限することもできます。

-   サービスを使用したアプリケーション開発の概要については、[開発者向けの概要](/docs/services/speech-to-text/developer-overview.html)を参照してください。
-   サービスの各インターフェースで使用する基本的な音声認識要求の例については、[認識要求の実行](/docs/services/speech-to-text/basic-request.html)を参照してください。

サービスの使用を簡素化するための SDK が多くのプログラミング言語用に提供されています。詳しくは、[API リファレンス ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/apidocs/speech-to-text){: new_window} を参照してください。

## 入力機能
{: #inputFeatures}

サービスの各インターフェースでは、音声をテキストに書き起こすための共通の入力機能が共有されています。

-   [音声フォーマット](/docs/services/speech-to-text/audio-formats.html) - 書き起こし可能な対象は、Opus または Vorbis コーデックを使用した Ogg または Web Media (WebM) 音声、MP3 (または MPEG)、Waveform Audio File Format (WAV)、Free Lossless Audio Codec (FLAC)、線形 16 ビット・パルス符号変調 (PCM)、G.729、A-Law、mu-law (または u-law)、および基本的な音声です。圧縮をサポートしているフォーマットを使用することで、単一の要求で送信できる音声データの量を最大化できます。
-   [言語とモデル](/docs/services/speech-to-text/models.html) - ほとんどの言語については、広帯域モデルまたは狭帯域モデルを使用して音声を書き起こすことができます。最低サンプリング・レートが 16 kHz である音声には広帯域モデルを使用してください。最低サンプリング・レートが 8 kHz である音声には狭帯域モデルを使用してください。
-   [音声の伝送](/docs/services/speech-to-text/input.html#transmission) - データ・チャンクの連続ストリームとして音声を渡すことも、1 回限りの送信としてすべての音声データを同時に渡すこともできます。ストリーミングの場合は、非アクティブとセッションの[タイムアウト](/docs/services/speech-to-text/input.html#timeouts)が適用されます。

## 出力機能
{: #outputFeatures}

各インターフェースでは、以下の共通の出力機能もサポートされています。

-   [話者ラベル](/docs/services/speech-to-text/output.html#speaker_labels)によって、米国英語、英国英語、スペイン語、または日本語の音声で個別の話者が識別されます。書き起こし結果では、複数の人物が参加している会話における各話者の発言がラベル付けされます (ベータ機能)。
-   [キーワード検出](/docs/services/speech-to-text/output.html#keyword_spotting)では、ユーザー定義の信頼度レベルに基づいて、指定されたキーワード・ストリングに一致する発話句が識別されます。キーワード検出が特に役に立つのは、書き起こし内容全体よりも音声に含まれる個別の句の方が重要な場合です。例えば、お客様サポート・システムでは、識別されたキーワードに基づいてユーザーの要望の転送先を決定できます。
-   [中間結果](/docs/services/speech-to-text/output.html#interim)では、書き起こしの進行中に漸進的な仮説が返されます。書き起こしが完了した時点で、最終結果が返されます。中間結果を提供できるのは、WebSocket インターフェースのみです。
-   [最大候補数](/docs/services/speech-to-text/output.html#max_alternatives)では、可能性のある書き起こし候補が返されます。サービスでは、信頼度が最も高い最終結果が提示されます。
-   [単語候補](/docs/services/speech-to-text/output.html#word_alternatives)では、書き起こし結果に含まれる単語に音響的に類似している単語候補が提示されます。
-   [単語の信頼度](/docs/services/speech-to-text/output.html#word_confidence)では、書き起こし結果に含まれる各単語の信頼度レベルが返されます。
-   [単語のタイム・スタンプ](/docs/services/speech-to-text/output.html#word_timestamps)では、書き起こし結果に含まれる各単語の開始と終了のタイム・スタンプが返されます
-   [スマート・フォーマット設定](/docs/services/speech-to-text/output.html#smart_formatting)では、日付、時刻、数値、金額、電話番号、およびインターネット・アドレスが、読みやすい標準的形式に変換されて、最終書き起こし結果に出力されます。米国英語の場合は、最終書き起こし結果で特定の句読点記号を追加するキーワード句を指定することもできます。スマート・フォーマット設定がサポートされているのは、米国英語、日本語、およびスペイン語の音声です (ベータ機能)。
-   [数値編集](/docs/services/speech-to-text/output.html#redaction)では、最終書き起こし結果で数値データを編集 (伏せ字) します。編集機能の目的は、クレジット・カード番号などの機密性の高い個人情報を書き起こし結果から削除することです。この機能がサポートされているのは、米国英語、日本語、および韓国語の音声です (ベータ機能)。
-   [禁止用語フィルター](/docs/services/speech-to-text/output.html#profanity_filter)では、米国英語の書き起こし結果に含まれる禁止用語が検閲されます。

## 言語サポート
{: #languages}

このサービスで提供されるモデルでサポートされている言語は、ブラジル・ポルトガル語、フランス語、ドイツ語、日本語、韓国語、北京語、現代標準アラビア語、スペイン語、英国英語、および米国英語です。サービスは、すべての言語ですべての機能をサポートしているわけではありません。さらにサービスは、一部の機能を一般出荷可能 (GA) として実動使用向けにサポートしている一方で、他の機能をベータ版としてさまざまな言語向けにサポートしています。

-   WebSocket インターフェースと HTTP インターフェースは、すべての言語で一般出荷可能です。
-   サービスでは、広帯域モデル、狭帯域モデル、または両方のモデルをさまざまな言語向けに提供しています。詳しくは、[言語とモデル](/docs/services/speech-to-text/models.html)を参照してください。
-   一部の音声認識機能は、特定の言語のみで使用できます。詳しくは、[パラメーターの要約](/docs/services/speech-to-text/summary.html)を参照してください。
-   言語モデル・カスタマイズ・インターフェースは、ほとんどの言語で一般出荷可能です。音響モデル・カスタマイズ・インターフェースは、すべての言語でベータ機能として使用できます。詳しくは、[各言語でのカスタマイズのサポート](/docs/services/speech-to-text/custom.html#languageSupport)を参照してください。

## 料金
{: #pricing-index}

サービスの価格プランについて詳しくは、[{{site.data.keyword.Bluemix_short}} カタログの {{site.data.keyword.speechtotextshort}} サービス ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/catalog/services/speech-to-text){: new_window} を参照してください。月々の使用料の価格設定と事例に関する質問の回答については、[価格設定に関する FAQ](/docs/services/speech-to-text/faq-pricing.html) を参照してください。

## サービスの試用
{: #tryOut}

{{site.data.keyword.speechtotextshort}} サービスの実際の動作の例については、以下を参照してください。

-   [クイック・デモ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://speech-to-text-demo.ng.bluemix.net/){: new_window} では、ストリーミング入力された音声またはアップロード・ファイルに含まれる音声をテキストに書き起こすことができます。
-   {{site.data.keyword.ibmwatson}}[Starter Kit ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} に含まれるアプリケーションによって、サービスの使用法が示されます。
-   {{site.data.keyword.watson}} ブログ投稿 [Getting robots to listen: Using {{site.data.keyword.watson}}'s {{site.data.keyword.speechtotextshort}} service ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/blogs/watson/2016/07/getting-robots-listen-using-watsons-speech-text-service/){: new_window} では、サービスの WebSocket インターフェースを Python と組み合わせて使用して、音声から発話を抽出する方法を説明しています。この投稿は、必要なコードと手順を紹介する詳細なチュートリアルになっています。
