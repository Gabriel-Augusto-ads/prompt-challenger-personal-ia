## 🛠️ Levantamento Técnico baseado nas Regras de Negócio

### 1. Seleção do Biotipo Corporal
- **Objetivo**: Capturar e categorizar o biotipo corporal do usuário para personalizar o plano de treino.
- **Entrada**: 
  - O personal trainer deve selecionar o biotipo corporal do usuário entre as opções: 
    - **Ectomorfo**: Corpo mais magro, dificuldade para ganhar peso e massa muscular.
    - **Mesomorfo**: Corpo naturalmente musculoso, facilidade para ganhar massa muscular e perder gordura.
    - **Endomorfo**: Tendência a acumular gordura, maior dificuldade em perder peso.
- **Saída**: 
  - Variável `{{biotipo}}` que define o tipo de treino adequado com base na escolha do personal trainer.
  - Exemplos de condições de treino:
    - Se `{{biotipo}}` for **Ectomorfo**: foco em treinos de resistência e volume.
    - Se `{{biotipo}}` for **Mesomorfo**: treinos balanceados de força e resistência.
    - Se `{{biotipo}}` for **Endomorfo**: treinos focados em queima de gordura e aumento de massa magra.

### 2. Determinação dos Dias Disponíveis para Treino
- **Objetivo**: Determinar quantos dias por semana o usuário pode treinar, influenciando a estrutura do plano de treino.
- **Entrada**: 
  - O personal trainer deve informar a quantidade de dias disponíveis para treino, com base na agenda do usuário:
    - **1 dia**: Treino Full Body.
    - **3 dias**: Treino ABC (divisão em três partes).
    - **5 dias**: Treino ABCDE (divisão em cinco partes).
- **Saída**: 
  - Variável `{{dias_treino}}` que determina o tipo de treino sugerido.
  - Mapeamento dos tipos de treino sugeridos:
    - Se `{{dias_treino}}` for **1** → `Full Body`
    - Se `{{dias_treino}}` for **3** → `ABC`
    - Se `{{dias_treino}}` for **5** → `ABCDE`

### 3. Seleção do Tipo de Exercício
- **Objetivo**: Capturar a preferência do usuário em relação ao tipo de exercício, promovendo maior adesão ao plano de treino.
- **Entrada**: 
  - O personal trainer deve escolher entre os seguintes tipos de exercício, com base nas preferências do usuário:
    - **Funcional**: Exercícios que melhoram a funcionalidade do corpo, usando movimentos naturais.
    - **Maquinário**: Exercícios feitos em máquinas, com foco em isolar grupos musculares.
    - **Peso Livre**: Exercícios com pesos livres (halteres e barras), para trabalhar vários grupos musculares simultaneamente.
    - **Cardio**: Exercícios para melhorar a resistência cardiovascular, como corrida ou ciclismo.
    - **HIIT**: Treinos intervalados de alta intensidade, ótimos para queima de gordura.
- **Saída**: 
  - Variável `{{tipo_exercicio}}` que guiará a seleção de exercícios no plano de treino.
  - Exemplo de estrutura de seleção:
    - Se `{{tipo_exercicio}}` for **Funcional**, o plano incluirá exercícios como agachamentos, flexões e levantamento de terra.

### 4. Geração do Plano de Treino Personalizado
- **Objetivo**: Criar um plano de treino individualizado com base nas informações coletadas (`{{biotipo}}`, `{{dias_treino}}` e `{{tipo_exercicio}}`).
- **Entrada**: 
  - Variáveis de entrada: `{{biotipo}}`, `{{dias_treino}}`, `{{tipo_exercicio}}`.
- **Saída**: 
  - Um plano de treino estruturado que incluirá:
    - **Frequência dos treinos**: com base em `{{dias_treino}}`.
    - **Grupos musculares trabalhados**: definidos de acordo com a divisão escolhida (Full Body, ABC, ABCDE).
    - **Tipos de exercícios a serem realizados**: adaptados ao `{{tipo_exercicio}}` selecionado.
    - **Exemplo de Plano**:
      - Para um usuário com `{{biotipo}}` mesomorfo que treina `{{dias_treino}}` 3 dias por semana e prefere `{{tipo_exercicio}}` pesos livres:
        - **Dia 1**: Peito e Tríceps - Supino, Tríceps Testa.
        - **Dia 2**: Costas e Bíceps - Remada, Rosca Direta.
        - **Dia 3**: Pernas e Ombros - Agachamento, Desenvolvimento.

### 5. Análise de Dados do Usuário
- **Objetivo**: Coletar e analisar dados de usuários para personalizar ainda mais os treinos.
- **Entrada**: 
  - Informações demográficas (`{{idade}}`, `{{sexo}}`, `{{nivel_experiencia}}`).
  - Objetivos do usuário (`{{objetivos}}` - perda de peso, ganho de massa muscular, melhoria de performance).
- **Saída**: 
  - Dados agregados para entender tendências e padrões, ajudando a ajustar os treinos propostos.

### 6. Feedback do Usuário
- **Objetivo**: Capturar feedback sobre a eficácia dos treinos gerados.
- **Entrada**: 
  - O usuário pode avaliar a dificuldade dos treinos e relatar se alcançou seus objetivos (`{{avaliacao}}`).
- **Saída**: 
  - Ajustes nos planos de treino futuros com base nas avaliações do usuário, permitindo melhorias contínuas.

### 7. Integração com Dispositivos de Monitoramento
- **Objetivo**: Integrar com dispositivos como smartwatches ou aplicativos de fitness para monitorar desempenho.
- **Entrada**: 
  - Dados em tempo real de frequência cardíaca (`{{frequencia_cardiaca}}`), calorias queimadas (`{{calorias_queimadas}}`) e repetições (`{{repeticoes}}`).
- **Saída**: 
  - Relatórios de desempenho que ajustam automaticamente os planos de treino conforme necessário.

### 8. Personalização Avançada de Treinos
- **Objetivo**: Criar algoritmos que possam adaptar treinos baseados no progresso do usuário.
- **Entrada**: 
  - Histórico de treinos (`{{historico_treinos}}`), mudanças no `{{biotipo}}` e `{{feedback}}`.
- **Saída**: 
  - Recomendações de novos treinos, variações ou ciclos de treino para manter a motivação e eficácia.

### 9. Desenvolvimento de um Módulo de Dicas e Motivação
- **Objetivo**: Oferecer suporte motivacional e dicas de saúde.
- **Entrada**: 
  - Preferências do usuário em relação ao tipo de dicas (`{{tipo_dicas}}` - nutrição, motivação, técnicas de recuperação).
- **Saída**: 
  - Mensagens automáticas de motivação, sugestões de receitas saudáveis ou práticas de recuperação.

### Considerações Técnicas
- **Prompt Engineering**:
  - O prompt deve ser claro, estruturado e amigável para coletar as informações necessárias de forma eficiente.
  - Devem ser consideradas validações para entradas incorretas (por exemplo, garantir que o personal trainer escolha um biotipo válido).
  
  ```plaintext
  "Por favor, informe o biotipo corporal do usuário (Ectomorfo, Mesomorfo, Endomorfo), quantos dias por semana ele pode treinar (1, 3 ou 5) e seu tipo de exercício preferido (Funcional, Maquinário, Peso Livre, Cardio, HIIT)."
