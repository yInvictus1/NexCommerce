# NexCommerce - Sistema de Recomendação E-commerce com A/B Testing

## 📋 Sobre o Projeto

NexCommerce é um sistema completo de recomendação de produtos para e-commerce, desenvolvido para demonstrar habilidades em ciência de dados, engenharia de machine learning e experimentação. O projeto implementa múltiplos algoritmos de recomendação e inclui um framework de A/B testing para avaliar performance em métricas de negócio.

## 🎯 Objetivos de Aprendizado

Este projeto foi criado para consolidar conhecimentos de nível júnior em:

- **Machine Learning**: Implementação de algoritmos de recomendação do zero
- **Engenharia de Dados**: Pipeline ETL completo e feature engineering
- **MLOps**: Versionamento de modelos, API REST e deploy
- **Experimentação**: A/B testing e análise de métricas de negócio
- **Boas Práticas**: Código limpo, documentação e testes

## ⚙️ Funcionalidades

### Algoritmos de Recomendação

#### Content-Based Filtering
- Recomendações baseadas em características dos produtos
- Similaridade de conteúdo (descrição, categoria, preço)
- Perfil do usuário construído a partir do histórico

#### Collaborative Filtering
- Filtragem colaborativa user-item
- Identificação de usuários similares
- Recomendações baseadas em padrões coletivos

#### Hybrid Approach
- Combinação ponderada dos dois métodos anteriores
- Balanceamento automático baseado em contexto
- Solução para cold-start problem

### Pipeline de Dados

```
Raw Data → ETL → Feature Engineering → Model Training → Evaluation → Deploy
```

**Componentes:**
- **ETL**: Extração, limpeza e transformação de dados de usuários e produtos
- **Features**: Engenharia de features comportamentais e de conteúdo
- **Training**: Treinamento automatizado com validação cruzada
- **Deployment**: API REST pronta para produção

### A/B Testing Framework

Simulação de tráfego com grupos de controle e tratamento, incluindo análise de:

- **CTR (Click-Through Rate)**: Taxa de cliques nas recomendações
- **Conversion Rate**: Taxa de conversão em compras
- **Average Order Value**: Valor médio por pedido
- **Revenue per User**: Receita por usuário
- Cálculo de significância estatística

## 🛠️ Stack Tecnológico

- **Python 3.8+**
- **Pandas & NumPy**: Manipulação de dados
- **Scikit-learn**: Algoritmos de ML
- **FastAPI**: API REST
- **SQLite/PostgreSQL**: Armazenamento de dados
- **Plotly/Matplotlib**: Visualizações
- **Pytest**: Testes automatizados
- **Docker**: Containerização (opcional)

## 📁 Estrutura do Projeto

```
nexcommerce/
├── data/
│   ├── raw/              # Dados brutos
│   ├── processed/        # Dados processados
│   └── features/         # Features engineered
├── src/
│   ├── etl/              # Pipeline de ETL
│   ├── models/           # Implementação dos algoritmos
│   ├── evaluation/       # Métricas e A/B testing
│   └── api/              # API FastAPI
├── notebooks/            # Jupyter notebooks exploratórios
├── tests/                # Testes unitários
├── config/               # Arquivos de configuração
├── docs/                 # Documentação adicional
└── requirements.txt      # Dependências
```

## 🚀 Instalação e Execução

### Setup Inicial

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/nexcommerce.git
cd nexcommerce

# Crie um ambiente virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows

# Instale as dependências
pip install -r requirements.txt
```

### Executando o Pipeline Completo

```bash
# 1. ETL - Processar dados brutos
python src/etl/run_pipeline.py

# 2. Feature Engineering
python src/features/build_features.py

# 3. Treinar modelos
python src/models/train.py --model all

# 4. Executar A/B test simulado
python src/evaluation/ab_test.py --duration 7days

# 5. Iniciar API
uvicorn src.api.main:app --reload
```

### Endpoints da API

```bash
# Obter recomendações
GET /api/v1/recommendations/{user_id}?algorithm=hybrid&n=10

# Registrar interação (para A/B test)
POST /api/v1/interactions
{
  "user_id": "123",
  "product_id": "456",
  "interaction_type": "click"
}

# Visualizar resultados do A/B test
GET /api/v1/experiments/results
```

## 📊 Roadmap de Implementação

### Fase 1: Fundação (Semanas 1-2)
- Setup do projeto e estrutura de pastas
- Geração/coleta de dados sintéticos
- Pipeline ETL básico

### Fase 2: Modelos (Semanas 3-4)
- Content-based filtering
- Collaborative filtering
- Modelo híbrido

### Fase 3: API (Semana 5)
- API REST com FastAPI
- Endpoints de recomendação
- Documentação automática (Swagger)

### Fase 4: Experimentação (Semana 6)
- Framework de A/B testing
- Simulação de tráfego
- Dashboard de métricas

### Fase 5: Deploy (Semana 7-8)
- Containerização com Docker
- CI/CD básico
- Documentação final

## 📈 Métricas de Sucesso

### Métricas Técnicas
- Precisão @ K > 0.15
- Recall @ K > 0.20
- NDCG > 0.25
- Tempo de resposta < 200ms

### Métricas de Negócio (A/B Test)
- Aumento de CTR > 5%
- Aumento de conversão > 3%
- Significância estatística (p-value < 0.05)

## 🧪 Testes

```bash
# Executar todos os testes
pytest tests/

# Testes com cobertura
pytest --cov=src tests/

# Testes específicos
pytest tests/test_models.py -v
```

## 📚 Recursos de Aprendizado

- [Recommender Systems Handbook](https://link.springer.com/book/10.1007/978-1-4899-7637-6)
- [Fast.ai - Collaborative Filtering Deep Dive](https://course.fast.ai/)
- [Google's A/B Testing Best Practices](https://research.google/pubs/)
- [FastAPI Documentation](https://fastapi.tiangolo.com/)

## 🤝 Contribuindo

Este é um projeto de aprendizado, mas sugestões são bem-vindas.

1. Fork o projeto
2. Crie uma branch (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona MinhaFeature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 🔮 Próximos Passos

- Implementar deep learning (Neural Collaborative Filtering)
- Adicionar multi-arm bandit para otimização em tempo real
- Integrar com dados reais via web scraping
- Dashboard interativo com Streamlit
- Sistema de cold-start com transferência de aprendizado

---

**Desenvolvido para aprendizado e portfólio profissional**
