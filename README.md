# Análise de Sentimentos com Azure AI

## Descrição

Este projeto realiza a análise de sentimentos de textos utilizando a API do Azure Cognitive Services. O script lê frases de um arquivo de entrada, envia os dados para a API do Azure Language Studio.

## Insights e Possibilidades

- Permite análise de sentimentos automatizada para diferentes setores.
- Pode ser integrado em chatbots, suporte ao cliente e redes sociais.
- Expansível para outras análises como extração de entidades e detecção de linguagem.

## Configuração e Execução

1. **Criar um ambiente virtual**
   ```bash
   python -m venv venv  
   venv\Scripts\activate     # Windows
   ```

2. **Instalar dependências**
   ```bash
   pip install requests python-dotenv
   ```

3. **Configurar variáveis do Azure**
   Crie um arquivo `.env` e adicione suas credenciais:
   ```
   AZURE_ENDPOINT="https://<seu-endpoint>.cognitiveservices.azure.com/"  
   AZURE_KEY="<sua-chave>"  
   AZURE_REGION="<sua-região>"
   ```

4. **Inserir frases para análise**
   Edite o arquivo `inputs/sentencas.txt` com frases para análise, por exemplo:
   ```
   Estou muito feliz hoje!  
   Esse serviço foi péssimo.  
   A comida estava boa, mas o atendimento foi demorado.
   ```

5. **Executar o script**
   ```bash
   python main.py
   ```
   Isso gerará um arquivo `outputs/resultados.json` com os sentimentos detectados.

## Exemplo de Saída JSON

```json
{
  "sentence": "Estou muito feliz hoje!",
  "analysis": {
    "sentiment": "positive",
    "confidenceScores": {"positive": 0.99, "neutral": 0.01, "negative": 0.0}
  }
}
```
