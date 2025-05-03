# Furia Know Your Fan

Este projeto utiliza OCR (Reconhecimento Óptico de Caracteres) com a biblioteca Tesseract para extrair texto de imagens contendo documentos e verificar se um nome completo e um CPF informados pelo usuário estão presentes no conteúdo extraído, logo se as informações são válidas.

## 🔍 Funcionalidades

- Upload de imagens contendo documentos com dados pessoais.
- Extração de texto das imagens com o Tesseract OCR.
- Validação de CPF com algoritmo oficial.
- Verificação da presença do nome e CPF no texto extraído.

## 💡 Tecnologias Utilizadas

- Python
- Google Colab
- Tesseract OCR
- pytesseract
- PIL (Pillow)
- Expressões regulares (`re`)

## 🚀 Como Usar

1. **Abra o projeto no Google Colab.**
2. **Execute as células para instalar as dependências:**

```python
!sudo apt-get install -y tesseract-ocr
!pip install pytesseract
!sudo apt-get install tesseract-ocr-por
```

3. **Faça o upload da(s) imagem(ns) do documento:**

```python
from google.colab import files
uploaded = files.upload()
```

4. **Extraia o texto das imagens e verifique os dados informados:**

O script irá:
- Abrir cada imagem enviada.
- Extrair o texto usando `pytesseract` com o idioma português.
- Concatenar os textos.
- Solicitar nome completo e CPF do usuário.
- Validar o CPF com algoritmo oficial.
- Verificar se o nome e o CPF estão presentes no texto extraído.

5. **Interaja com a interface do console:**

Digite o nome completo e o CPF (somente números) quando solicitado.

## 📂 Exemplo de Uso

Suponha que você envie uma imagem de um documento que contenha:

```
Nome: JOÃO SILVA
CPF: 123.456.789-09
```

Ao rodar o script e informar:

- Nome: `João Silva`
- CPF: `12345678909`

O sistema responderá:

```
Nome e CPF encontrados no documento, identificacao valida!.
```

## 🧪 Validação de CPF

A função implementada segue a validação oficial do CPF, considerando os dois dígitos verificadores e ignorando CPFs com todos os dígitos iguais.
