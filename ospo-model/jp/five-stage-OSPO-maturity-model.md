# 組織のための OSPO モデルの分類

本文書では OSPO モデルについて分類体系を作り、さまざまな組織で学びや実装が促進できるよう重要なコンポーネント (やパターン) を明確にすることを目指しています。継続的にアップデートされ鮮度が保たれることが期待された文書でもあります。

コミュニティの皆さんも、「5 段階の OSPO 成熟度モデル」に特定の業種や地域のニーズにフィットした形でコントリビューションすることができます。

> コントリビューションに当たっては、ぜひPR（プルリクエスト） を出してください


## OSPO モデル 1 - 5 段階の OSPO 成熟度モデル

> 詳細な調査は、[The evolution of the OSPO](https://www.linuxfoundation.org/research/the-evolution-of-the-open-source-program-office-ospo) （日本語翻訳版：「[OSPO の進化](https://www.linuxfoundation.jp/publications/2022/05/the-evolution-of-the-open-source-program-office-ospo/)」）でご覧いただけます。
>
> OSPO の特性、構造、役割の詳細については、[A Deep Dive Into OSPO](https://www.linuxfoundation.org/tools/a-deep-dive-into-open-source-program-offices/) （日本語翻訳版：「[深層考察：『オープンソース プログラム オフィス』](https://www.linuxfoundation.jp/publications/2022/11/a-deep-dive-into-open-source-program-offices/)」）で確認ください。

OSPO の存在が浸透し、より一般的なものになるに従い、こういった OSS のプログラムが成熟してきました。そこで私たちは OPSO のリーダーや専門家たちとの対話を本サーベイ結果にマッピングすることで、OSPO の典型的な進化のステップを記述する OSPO 成熟度モデル (OSPO maturity model) を開発しました。すべてのケースに当てはまるものではないことには注意が必要ですが、このモデルは日常のオペレーションで「伝統的に」オープンソースが実装されることのなかった環境でも機能することを示してきました。また、組織の OSPO がどれだけ成熟しているのかは、規模や種類が作用していることもわかります。規模の大きな組織では、複数のビジネスユニットがあり、それぞれ異なった技術カルチャーで異なった形でオープンソースへのアプローチを編み出す可能性がありますし、純粋にデジタル技術を中軸にした企業では早期から OSS を消費したりプロジェクトにコントリビュートしたり、オープンソースの技術やコンセプトに触れる機会ははるかに多くなってきます。

![LFResearch_OSPO_Report_Fig2](https://github.com/nao027/ospology/blob/main/ospo-model/jp/ospo-maturity-model-jp.png)

**OSPO モデルを紐解く**

OSPO のレベルは、その実行力によって決まります。また、各ステージは積み上げる形でステップアップしていきます。これは、レベルが上がるごとに OSPO が前のレベルのタスクと責任も引き継ぐことを意味します。

たとえば、ある OSPO がオープンソースのコンプライアンスとセキュリティ（レベル 1）に関連する必要なタスクをすべてカバーするようになると、この OSPO はレベル 2 へ移行する準備ができた状態になっていきます。そしてその OSPO では、オープンソースの法的責任（レベル 1）と、OSS カルチャーの浸透やエコシステムへの参加に関連する責任（レベル 2）の両方を担うようになっていきます。

## 0️⃣ ステージ 0: オープンソースのアドホックな導入

今、ほとんどすべての組織で OSS が使われています。OSS の採用の仕方や初期段階での使い方はさまざまです。製品やツールの中でビルディングブロックやライブラリの一つとして OSS が使われるかもしれませんし、ベンダーのプロダクトスタックの主要部分となって使われていたり、ベンダーのサービスオファリングをサポートするときに使われていたりするのかもしれません。開発者たちが、ラピッドプロトタイピングやマイクロサービス、小さなアプリケーションのために OSS を使っているかもしれません。また、開発者たちは OSS の開発ツール ― 統合開発環境（IDE）や、GitHub、GitLab のようにオープンソースの上で構築されたツール類 ― をよく採用しています。モダンなクラウドネイティブ アプリケーションもまた、ほぼデフォルトの状態でコンテナオーケストレーション、可観測性（Observability）、データストレージ、メッセージングといった機能としてオープンソースのシステムを使用しています。アプリケーションのフロントエンドにおいても、開発者たちはオープンソースのライブラリやフレームワークをとても頼りにしています。Red Hat は、「ITリーダーの90%がエンタープライズ オープンソースを使用している」と報告しています。また、Synopsys のようなソフトウェア構造解析のベンダー企業が、すべてのコードベースの 75% 以上がオープンソースコンポーネントを含んでいると断定しています。

言い換えれば、ほぼすべての組織がオープンソースを使用している、ということです。しかし、非常に初期の段階での導入形態は場当たり的（アドホック）なもので、すぐに使えるツールや技術を開発者たちが駆使しながら、問題を解決しています。この「アドホック（場当たり的）な導入」は、通常デフォルトではない状況でのライセンスコンプライアンスや、オープンソースを消費（Consume）したり、オープンソースのコンポーネントを用いて構築されたプロダクトを配布したりすることによる長期的な影響について、ほとんど考慮されていないことを意味します。こういった段階のほとんどにおいて、少数のエンジニアが積極的にオープンソースを探し求めている一方でエンジニアリング組織のその他のメンバーたちは ― たまたまオープンソースを使用していたとしても ― その活動がオープンソースに依存しているとは見なしていません。帰結としてその組織にはオープンソースに焦点を当てた中核的チームも、組織にとってのトップレベルのオープンソース戦略も存在していません。これらは非常に危機的な状況と言えます。なぜならば、前述したようなオープンソースのコンポーネントが採用されるとそれらがそのまま組織のソフトウェアサプライチェーンの一部となることから、そういった状況に対する戦略的なアプローチはなくてはならないものになってくるからです。

## 1️⃣ ステージ 1: OSS コンプライアンス、インベントリ、開発者教育の提供

一般的に、組織がOSPOを形成するのは、ほぼすべてのエンジニアリングおよび開発の部門・機能にわたって人々がオープンソースの製品とコードを消費していることに気づいたときです。この使用は通常組織内部的な使用であり、顧客またはユーザー向けに提供された製品またはサービスの一部にはなっていない状況です。実際のところ、かなりのIT機能を持ち、高度なオンラインまたはアプリケーションでプレゼンスを持つすべての組織がオープンソースを使っています。その理由は、技術スタック全体を見るとオープンソースがいたるところ ― Linux サーバや MySQL データベースにはじまり、Node.js や Python などのプログラミング言語、さらには React や Vue.js などのフロントエンドフレームワークといったあらゆるところ ― に存在しているという点にあります。

この初期の段階では、組織はしばしば OSPO に対しいろいろな名称を用います。たとえば IBM では、当初自社のオープンソースの活動主体を「オープンソース運営委員会（Open Source Steering Committee）」と呼んでいました。しかし、すべての場合において、ステージ 1 の段階にいる組織は、OSS がビジネス戦略およびテクノロジー戦略の重要な部分であることを認識しています。そして彼らは、OSS プロジェクトのセキュリティプラクティスがプロプライエタリなソフトウェア会社のそれと異なっていることを理解しています。例えば、OSS プロジェクトのディスクロージャールールは、プロプライエタリなプロジェクトよりも厳しい傾向にあります。そのため、彼らにとっての法的およびセキュリティ上のリスクは明確にしなければならないのです。リスク低減戦略としては、ライセンシングにおける配慮、開発者教育、および厳密なインベントリ作成などが挙げられます。

### リーガルリスクとライセンスを管理する

組織の法務チームや技術リーダーは、従業員（外注先、サプライヤなど含む）全員がライセンス条項に従って OSS を使用し、かつ組織の OSS の消費で法的リスクにさらされていないことを担保する目的で、OSPO のステージ 1 の開発を開始する傾向があります。使われている OSS ライセンスは多数あります。2020年の調査では、回答者は大企業における OSPO のメリットとして「コンプライアンス」をトップとしていました。中規模企業でもコンプライアンスは 2 番目に優れたメリットとなっています。多くの企業はたいてい混乱のもとでスタートします。

OSS ユーザーの人たちはいつも法令遵守を考慮してきたのですが、一部の OSS コントリビューターたちは、大規模クラウドプロバイダがオープンソース プロジェクトに基づいてプロプライエタリなサービスを作成することを思いとどまらせるべく、新しいライセンスをデザインしてきました。その中で最も際立ったものが、Affero General Public License（AGPL）です。このライセンスの条項に基づきリリースされた OSS をある企業が使用し、プロプライエタリな SaaS（Software-as-a-Service）を顧客に提供する可能性がありますが、AGPL の条項で内部向けのデリバリと外部向けのデリバリを明確に区別できない場合、その OSS の作成者はその企業をライセンス違反で訴訟する根拠を持つ可能性があります。また、多くの企業では、社内ユニット間で内部課金システムがあり（外部向けの）有料サービスと内部向けサービスの境界がさらに曖昧になってきます。

### 開発者たちを教育する

コンプライアンスを維持するために、OSPO 成熟度「ステージ 1」の段階にある組織は、教育プログラムを作成して、開発者たちが新しいプロダクトやサービスを開発する際、「いつ」OSS を使用するか、を判断できるようにサポートします。「オープンソースの教育を受けていない開発者たちの多くは、自分たちはソフトウェアを購入しているわけではなく、また契約書に署名するわけでもないので、ライセンス自体が存在していないと考えるのです」と VMware のオープンソース マーケティング&ストラテジー担当ディレクターの Suzanne Ambiel は言います。「オープンソースソフトウェアはたぶん『無料』の意味での『フリー』なのでしょう。それを正しく使わなければコストがかかってしまうのに。OSS には必ずライセンスがついてきます。OSPO の最も重要な役割の 1 つは、さまざまなライセンス選択の含意を開発者たちが理解することを確かにすることなのです」

開発者教育を通じ、上位管理層が OSS の価値や重要性を認識することもよくあります。このようなプログラムでは、開発者たちが学ぶのは次のようなことです。

* 異なるライセンスタイプの微妙な違い（ニュアンス）
* 新たに OSS プロダクトを導入するための正式な承認プロセス
* 正式なライセンスがないプロジェクトやコードの OSS の使用を含め、「準拠していない」OSSの消費に関する実際のリスク
* オープンソースにコントリビュートする自組織の開発者たちを対象とした CLA（Contributor License Agreements）の使用

このステージで、組織として正式な　CLA ポリシーが導入されることもあります。また、組織の技術スタックもしくはインフラでどの OSS を使用するかを決定する基準の一部として、OSS プロジェクトの健全性を判断するガイダンスを提供するケースもあります。 

### ソフトウェアインベントリを取得する

開発者たちが自らの取り組みをシステマチックにカタログ化することなく、アドホックに OSS デプロイしているかもしれません。法務チームや技術リーダーは、組織内で使用されているすべての OSS について棚卸しすることを強く求める傾向があります。このようなインベントリによって、組織のコードリポジトリ（例：GitHub、GitLab）やシステムにある OSS がアイテム化されていきます。ステージ 1 の段階にある組織は、具体的なソフトウェアインベントリ プロセスを起こし、組織全体のソフトウェア部品表（SBOM）を作成します。このインベントリを用い法務チーム ― 通常は OSPO チームと連携します ― は、OSS の使用状況を継続的にモニタリングし、法的リスク、セキュリティリスク、その他のプロジェクトリスクにフラグを立てることができるようになります。詳細に書かれた SBOM によって、最高技術責任者（CTO）や最高情報責任者（CIO）などのテクノロジーリーダーシップが、最もビジネス クリティカルな使い方や組織上のセキュリティを認識しこれらをしっかり監視します。

**このステージで参加を推奨する OSS コミュニティのリスト**

| 横断的スキル | プロジェクト / コミュニティ |
| --- | --- |
| コンプライアンス | OpenChain |
| セキュリティ | OpenSSF |
| | SPDX |

> 他にも該当するオープンソース コミュニティはありますか？ ぜひPR（Pull Request） を出してください

## 2️⃣ ステージ 2: OSSの使用とエコシステムへの参加の啓発

OSSの価値やコンプライアンス、教育、SBOM といったことの必要性を組織が認識するようになると、その次に組織は OSS の使用による経済的なメリットを享受し、それを広げようとし始めます。ステージ 2 の段階にある OSPO は、承認された OSS プロダクトの使用を推進する「アンバサダー」として、OSS の良好な衛生環境についての教育プログラム、OSS におけるスキルアップや認定のための技術トレーニングや費用負担といった組織内の仕組みを作り上げていきます。こういったイニシアチブを通じ組織は OSS の使用を広げることができ、「OSS は重要なだけでなく、プロプライエタリなソフトウェアプロダクトよりも望ましく、好ましいものだ」というわかりやすいメッセージを出すこともできてきます。

従業員向け教育では、OSS プロジェクトとの連携で得られたベストプラクティス ― 機能実装の要求（Feature request）の仕方、バグレポートの出し方、基本コード（Basic code）のコントリビューションの仕方など ― について説明されることもあります。このステージの間組織は自らのコラボレーションの「筋肉」を鍛え、OSS プロジェクトやコミュニティの「社会生活」を経験することになります。またこの段階において、OSPO は従業員や管理者に向け、OSS の単なる消費でなく、OSS へのコントリビューションの重要性も伝えるようになります。こういた「アウトリーチ」には、イベント スポンサーシップの提唱や推進、公開コーディングフォーラムでのプロジェクトリーダーやメンテナーの講演者・パネリストとしての登壇の調整、ミッションクリティカルな OSS プロジェクトへの組織内リソース（人材やファンドなど）の確保、といったものも含まれます。 

また、組織にとって積極的で目に見える参加は、可視性を高め、評判を上げ、雇用者の魅力を向上させる、といった多重の恩恵を生み出すものにもなります。この目的から、非テック組織（Non-tech organization）の多くがコミュニティとの交流を深め、OSS エコシステムの中で働くことを楽しむ開発者たちをリクルートするべく、際立った OSS イベントで有償ブースを活用しています。オープンソースに積極的なテック企業は、OSS コミュニティやベンダーとの交流を望む顧客に対して教育プログラムを拡張して提供するのかもしれません。「オープンソースへの参加方法や、プロジェクトへのコントリビューションやコラボレーションの仕方について、顧客から非常にたくさんのリクエストをもらいます」と、言うのは Red Hat のオープンソース担当シニアディレクターの Deborah Bryant です。

ステージ 2 の段階を進んでいくにつれ、組織は自社の事業運営にとって重要性の高い OSS プロジェクトに開発者たちが取り組み、活動的コントリビューター、主要メンテナーのレベルを目指せるようインセンティブを提供するようになります。テック企業にとって、卓越した OSS プロジェクトのコントリビューターを雇用することは価値ある投資です。たとえば、Linux カーネル ― Linux オペレーティングシステムのコアコンポーネントであり、コンピュータハードウェアとソフトウェアの間の重要なインターフェイスでもあります ― へのコントリビューターのほとんどは、Linux 用のコードを書くことを職務とする、フルタイムの従業員（FTE：Full-time employee）です。

テクノロジー部門以外で、フルタイムの社員たちをオープンソースの仕事に割り当てることができる組織はほとんどないのですが、そうしようとする動きがあります。例えば、Comcast と Bloomberg の両社には OSS プロジェクトに取り組むフルタイムの従業員がいます。このステージで、OSPO は開発者が OSS を消費するためのプロセスをいかにして合理化するか、模索し始めるようになります。そういった開発者の効率面としては、CLA の簡素化、許容できるライセンスタイプの OSS をチケッティングシステムへ追加する際の承認の迅速化、OSS アーキテクチャやソフトウェアの再利用の促進（別形態のインナーソーシング）、ライブラリの選択やオープンソース開発ツールの標準化、といったものがあり、結果として OSPO とプラットフォームの運用が「混ざり合う」ようになります。

通常 OSPO 成熟サイクルの「ステージ 2」において、OSPO は自社開発者のためのアウトバウンドのソースコントリビューションの合理化や最適化に取り組むようになります（ソフトウェアまたはコアテクノロジー企業においてはこれが「ステージ 1」の場合もあります）。アウトバウンドへの参加にかかる申請・承認プロセスは、通常場当たり的で、当初は痛みを伴うものでもあります。

**このステージで参加を推奨する OSS コミュニティのリスト**

| 横断的スキル | プロジェクト / コミュニティ |
| --- | --- |
| コミュニティの健全性とメトリクス | CHAOSS |
| 社内のオープンソース文化 | InnerSource Commons |

> 他に該当するオープンソース コミュニティはありますか？ぜひPR を出してください

## 3️⃣ ステージ 3: OSSプロジェクトのホストとコミュニティの育成

ステージ 3 では、組織がOSSプロジェクトを一から立ち上げ、その後はホストや主要スポンサーの役割で活動します。彼らは 1 人以上のフルタイムの従業員をそのプロジェクトに専念させるようになっていきます。また彼らはプロジェクトのコミュニティを育成し、その健全性を確保する責任も担います。彼らは、この組織としてコミットするレベルの話をプロジェクトをオープンソース化すると決めた社員個人レベルでの話と混同せず、分けて考えます。ステージ 3 の段階では、組織のリーダーたちがオープンソース プロジェクトのインキュベーションやパブリック領域での立ち上げをサポートします。これは、オープンソースプロジェクトが組織にとってどのようなメリットがあるのかを理解していることに起因します。このようなプロジェクトは、重要なケイパビリティ ― 組織のバリュープロポジション（Value proposition：価値提案/価値命題）の中核ではなくとも、テクノロジーのインフラで必要不可欠の大事なケイパビリティ ― として、より優れたパフォーマンスや経済性を発揮することに繋がります。 

さらに、オープンソースプロジェクトを一から立ち上げる組織は、オープンソースコミュニティにおいて幅広い信頼を確立します。オープンソースの技術に取り組むことで広がる可能性は多くの開発者にとって魅力的なのです。私たちが話をした OSPO の大半が、オープンソースの取り組みでの主なモチベーションとして、エンジニアリング人材の新規採用と既存人材の定着を挙げていました。

フルタイムの従業員とファンディングによってプロジェクトをサポートすることは、オープンソースにおける「成果を得るための真の投資（True skin in the game）」です。この「しきい」を越え、多発的にオープンソースプロジェクトを成功裏に立ち上げる組織は、立ち上げたその後でこういったプロジェクトをインキュベートし、その成功を確実にできるよう内部リソースとプロセスを発展させていきます。OSPO は、プロジェクトの組成、立ち上げのためのゲートキーパーやメンターであるだけでなく、健全なオープンソース エコシステムを育成する上での要諦についてプロジェクト立ち上げメンバを教育したり、OSSプロジェクトに求められる、より公的な役割としてリーダーシップを発揮できるようにプロジェクトリーダーたちをコーチしたりもします。 

OSS な組織として成熟してくるとその組織の OSPO はオープンソースプロジェクトを把握し、まとめ、運用していくための内部プロセス、プレイブック、チェックリスト、ツールやその他の仕組みを整備し、そしてそ先を見据えそのリーダーたちをコーチします。OSPO の中には、主要なオープンソースの財団や TODO Group などの協力機関の支援のもとでプロジェクトを立ち上げ、ケイパビリティを高め、インフラ、戦術的な支援、その他リソースを提供したりするやり方を好むところもあります。この方向性では、リソース集約性は相対的に低くなりますが、プロジェクトのコントロールがより広範なコミュニティに委ねられることになります。

**このステージで参加を推奨する OSS コミュニティのリスト**

| 横断的スキル | プロジェクト / コミュニティ |
| --- | --- |
| コミュニティの健全性とメトリクス | CHAOSS |
| 特定のプロジェクトと傘下財団 | Linux Foundation |
| | CNCF |
| | Eclipse Foundation |
| | Apache Foundation |

> 他にも該当するオープンソースコミュニティはありますか？ ぜひPR を出してください

## 4️⃣ ステージ4：戦略的意思決定のパートナー化

この成熟段階では、OSPO は技術的な決定に対する戦略的パートナーとなり、プロジェクトへの長期的なコミットメントの選択や形成へ導く手助けをするようになります。ステージ 4 では、CTO をはじめとする技術リーダーたちが、どういったオープンソース技術にたよるべきか、どういった判断基準をオープンソースプロジェクトの審査において設けるべきか、といったことついて OSPO やそのリーダーたちと協議します。重大なオープンソース技術の選択は、著しい二次的、三次的コストを生じさせ、さらに上流および下流の技術や雇用計画にも影響を与える傾向があるため、オープンソースプロジェクトの選択は大きなビジネス上の意思決定となってきます。 

大まかに言えば、OSPO は「ステージ 4」で3種類の戦略的ガイダンスを提供します。第 1 に、OSPO は、CTO と技術リーダーに対して、自組織の技術スタックからどのオーンソース技術を採用または除去すべきか、について助言します。図で示したように、今日の多くの OSS オプション ― ほとんどの主要なソフトウェアカテゴリは何十もの選択肢があります ― を考えると、OSPO は開発言語の人気、API の設計、各種 NoSQL データベースの能力といった、OSS のトレンドに関する洞察を提供することができます。この役割においては、OSPO は CTO の内部技術コンサルタント、そしてOSSに関する社内の専門家になっています。

第 2 のタイプの戦略的ガイダンスとしては、OSPO が主導し、「受け入れ可能」となっている OSS プロジェクトの構成要素に対しベンチマークを行います。OSPO はしばしば、プロジェクトの動向やパフォーマンス、特に使用を制限するライセンスタイプの変更やプロジェクト ロードマップの突発的な変更などを評価し、プロジェクトマネージャの頭の中でコミュニティに最大の関心が置かれているのかどうか、判定します。ほとんどの OSPO が、プロジェクトの挙動を評価するために、次のような手軽なメトリックをたよりにしています。

* ライセンスの種類は何か？
* そのプロジェクトの行動規範とはどんなものか、それを破ることがどのような結果につながるのか？
* ガバナンスの体制はどうなっているか、独立性が担保されているか？
* プルリクエストやバグ報告に対応するのに、どれくらいの時間がかかっているか？
* どのくらいの頻度で新しいバージョンをリリースしているか？
* そのプロジェクトをコントロールしているのは、1つ（企業や組織）なのか、コミュニティ全体なのか？
* プロジェクトに何人のコントリビューターがいるのか？こういった数字が時間の経過とともにどのように変化してきたか？

ガイダンスの 3 番目のタイプでは、組織がプロジェクトの「政治」を理解し、切り抜けていくことを支援します。例えば、多くの点で影響力がある関係者がプロジェクトを運営しようとする場合に中立な立場を維持することや、コミュニティメンバーが見せていない政治的考えを明らかにすることなど、がそれにあたります。より高いレベルでは、OSPO は企業が「テクノナショナリズム」に中立的な姿勢を維持し、国境や政治的領域を越えた人的、実務的な関係を育むことで、政治的な違いを橋渡しすることを支援します。こういった領域がオープンソースにおける重要な「中立的空間」となるにつれ、この価値が次第に財団（Foundation）や非営利団体（Non-profit）の活動にまで広がっていきます。

**このステージで参加を推奨する OSS コミュニティのリスト**

| Horizontal Skills | Project / Community |
| --- | --- |
| コミュニティの健全性とメトリクス | CHAOSS |
| 特定のプロジェクトと傘下財団 | Linux Foundation |
| | CNCF |
| | Eclipse Foundation |
| | Apache Foundation |

> 他に該当するオープンソース コミュニティはありますか？ぜひPR を出してください