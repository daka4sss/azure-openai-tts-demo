# Azure OpenAI GPT-4o Mini TTS Demo

Azure OpenAI GPT-4o Mini TTS（Text-to-Speech）API を使った実験用デモプロジェクトです。Gradio ベースのサウンドボード UI と、さまざまな音声や雰囲気でテキストから音声を生成するサンプルスクリプトを含んでいます。

![AOAI TTS Soundboard](assets/aoai-tts-soundboard.gif)

## Features

- Gradio によるインタラクティブなサウンドボードで、さまざまな音声や雰囲気を試せます
- TTS 音声のストリーミングや保存を行うサンプルスクリプトを同梱
- Azure OpenAI リソースに簡単に設定可能

## Getting Started

### Prerequisites

- Python 3.8+
- `eastus2` リージョンで作成された Azure OpenAI リソース、および GPT-4o Mini TTS モデルが Global Standard デプロイタイプでデプロイされていること

### Deploy GPT-4o Mini TTS Model with Azure AI Foundry
GPT-4o Mini TTS モデルをすばやくデプロイする手順：
1. [Azure AI Foundry portal](https://ai.azure.com/) にサインインします
2. **Catalog** に移動し、**Azure OpenAI** でフィルターし、`gpt-4o-mini-tts` を選択.
3. **Deploy** をクリックし、リソースを選択または作成し、デプロイ名を入力.

**Deploy** を再度クリックして完了します。.

詳細な手順については、完全なデプロイガイド をご覧ください。 [full deployment guide](https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/deploy-models-openai).

### Installation

1. リポジトリをクローンします：:
   ```sh
   git clone https://github.com/Azure-Samples/azure-openai-tts-demo.git
   cd azure-openai-tts-demo
   ```
2. 仮想環境を作成して有効化します:
   ```sh
   python -m venv .venv
   source .venv/bin/activate
   ```
3. 依存関係をインストールします:
   ```sh
   pip install -r requirements.txt
   ```

### Configuration

1. `.env.example` を `.env` にコピーし、Azure OpenAI のエンドポイントと API キーを記入します:
   ```sh
   cp .env.example .env
   # Edit .env with your values
   ```
   例:
   ```env
   AZURE_OPENAI_ENDPOINT="https://<your-resource-name>.openai.azure.com/"
   AZURE_OPENAI_API_KEY="your-azure-openai-api-key"
   AZURE_OPENAI_API_VERSION="2025-03-01-preview"
   ```

## Running the Demo

### Gradio サウンドボード UI

インタラクティブなサウンドボードを起動するには:

```sh
python soundboard.py
```

- 音声と雰囲気を選び、Play をクリックすると音声が生成され再生されます.

### Sample Scripts

- `streaming-tts-to-file-sample.py`: 音声をファイルにストリーミング保存.
- `async-streaming-tts-sample.py`: 音声を非同期でストリーミング再生.

スクリプトの実行例:
```sh
python streaming-tts-to-file-sample.py
```

## リソース

- [Azure OpenAI Service Documentation](https://aka.ms/oai/docs)
- [Blog Announcement](https://placeholder)

## Responsible Use and Content Requirements

このサウンドボードまたはその出力を使用する際は、[Microsoft Enterprise AI Services Code of Conduct](https://learn.microsoft.com/en-us/legal/ai-code-of-conduct) に**必ず**従ってください。以下を含みますが、これに限りません：

- **開示義務：** 音声が AI によって生成されたものであることを明確に開示してください。合成音声が実在する人物のものであると誤認させるようなことはしないでください。  
- **禁止されている使用法：** 本ツールやその出力を使用して以下を行ってはいけません：
  - 他人を欺く、なりすます、誤情報を流す  
  - 有害、違法、または不適切なコンテンツ（ヘイトスピーチ、暴力、嫌がらせ、性的内容など）を生成・配布する  
  - 個人の機微な属性や感情状態を推測・模倣しようとする  
  - 恋愛・性的目的、またはなりすまし目的のチャットボットを作成する  
  - 法律や規制に違反する行為を行う  
- **人による監視：** 適切な人間の監視を行い、法的、財務的、人権に影響を与えるような重要な意思決定には使用しないでください。  
- **コンテンツの権利：** 入力するコンテンツに対する権利を有していること、出力の使用が責任あるものであることを保証してください。  
- **フィードバックと悪用報告：** ユーザーが生成されたコンテンツの問題や悪用を報告できる手段を提供してください。  

要件と制限の全リストは、[Microsoft Enterprise AI Services Code of Conduct](https://learn.microsoft.com/en-us/legal/ai-code-of-conduct) を参照してください。

## License

MIT ライセンス。詳細は [LICENSE.md](LICENSE.md) を参照してください。

---

**Disclaimer:**

このプロジェクトは教育目的および個人利用のためのものであり、OpenAI や Microsoft によって公式に承認・サポートされたものではありません。OpenAI の [openai.fm](https://openai.fm) インタラクティブサイトに触発されたものであり、Azure OpenAI Service 上でのモデル利用を開発者が理解するためのデモとして作成されました。  