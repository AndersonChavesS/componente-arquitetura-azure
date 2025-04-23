# Construindo Arquiteturas no Azure - Laboratório Prático

Repositório criado como parte das atividades do **Bootcamp Java Cloud Native - Bradesco** na plataforma [DIO](https://www.dio.me/).  
Exploração dos componentes de arquitetura do Azure com foco em geolocalização de dados e estrutura global.

## 🌍 Objetivos do Laboratório
- Explorar a **estrutura global do Azure** ([azure.microsoft.com](https://azure.microsoft.com)).
- Entender o mapeamento de **datacenters** ([datacenters.microsoft.com](https://datacenters.microsoft.com)).
- Analisar **regiões do Azure** e políticas de data residency.
- Praticar com exemplos de configuração de geolocalização.

---

## 📌 Componentes de Arquitetura do Azure

### 1. **Regiões e Geografias**
- **Regiões**: Pares de datacenters (ex: `Brazil Southeast` no Rio de Janeiro e `Brazil South` em São Paulo).  
- **Data Residency**: Escolha da região para armazenamento/processamento de dados, conforme requisitos legais (ex: LGPD).  

### 2. **Estrutura Global**
- **Datacenters**: Mapeados em [datacenters.microsoft.com](https://datacenters.microsoft.com).  
- **Redundância**: Replicação entre regiões para resiliência, sem sair da geografia selecionada.  

---

## 🔍 Análise das Imagens do Diretório `/images`
As imagens deste repositório ilustram:  
1. **Página "Select your geography"** no Azure:  
   - Seleção de regiões brasileiras (`Brazil South` em SP e `Brazil Southeast` no RJ).  
   - Explicação sobre **data residency**:  
     > *"Microsoft não armazena ou processa dados fora da geografia selecionada, mesmo para replicação."*  

2. **Navegação no Portal Azure**:  
   - Abas como *Overview*, *Select geography*, e *Additional resources*.  

---

## 🛠️ Prática: Configurando Data Residency
### Passo a Passo
1. **Acesse o [Portal Azure](https://portal.azure.com)**.  
2. Navegue até **"Data Residency"** (em *Security + Compliance*).  
3. Selecione a geografia (ex: `Brazil`) e a região (ex: `Brazil South`).  
4. Revise as políticas de replicação e conformidade.  

📌 **Exemplo de Configuração via CLI**:
```bash
az account set --subscription "Sua-Assinatura"
az group create --name "Grupo-Brasil" --location "brazilsouth"
