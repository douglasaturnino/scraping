<div align='center'>
<img src="https://github.com/douglasaturnino/scraping/assets/95532957/b75a4281-9f3d-4537-9ccf-f3726acf8e25"  width=700px/>
</div>
# projeto scraping ao vivo

Nesse projeto foi feito uma ETL para monitoramento de preços utilizando python e a biblioteca scrapy

Para o web scraping foi utilizada a biblioteca Scrapy para extrair dados do Mercado Livre, especificamente tênis de corrida masculino. Foi utilizada a [url]("https://lista.mercadolivre.com.br/tenis-corrida-masculino") para realizar a raspagem.

Em seguida foi feita a transformação dos dados e inserida no banco SQLite.

E por ultimo foi feita um dashboard usando o stremlit.

## Gerenciamento de dependências

Eu gosto de utilizar o Poetry como gerenciador de ambiente. Abaixo, mostro os passos para instalar o Poetry, ativar o ambiente e em seguida como utilizar o projeto.

Para instalar o pix e o poetry
```bash
pip install pipx && pipx install poetry
```

Eu particulamente gosto de instalar o ambienete de desenvolvimento junto com o codigo. Para que o poetry fassa isso utilize o comando

```bash
 poetry config virtualenvs.in-project true 
 ```

Agora finalmente podemos instalar as dependencias do projeto
```bash
poetry install
```

Todas vez que for mexer no codigo é precisso ativar o ambiente com o comando
```bash
poetry shell
```
## Utilização do Projeto

Para rodar o web scraping

```bash
scrapy crawl mercadolivre -o ../../data/data.jsonl
```

Para rodar o PANDAS tem que fazer isso dentro da pasta SRC

```bash
python transformacao/main.py
```

Para rodar o Streamlit tem que fazer isso dentro da pasta SRC

```bash
streamlit run dashboard/app.py 
```