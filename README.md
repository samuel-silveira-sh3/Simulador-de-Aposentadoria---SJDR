# Aposentadoria SJDR - Especificação do Simulador

## 1. Legislação que deve ser considerada

A base municipal principal é a Lei Municipal nº 4.048, de 23 de junho de 2006, que reestruturou o Instituto Municipal de Previdência de São João del-Rei – IMP. O próprio IMP disponibiliza atualmente o texto da lei. 

O Estatuto dos Servidores, Lei Municipal nº 5.038/2014, determina que a aposentadoria dos servidores efetivos ou dos estáveis pelo art. 19 do ADCT é concedida pelo IMP conforme a Constituição Federal e suas Emendas Constitucionais. 

Isso é importante porque o simulador não pode considerar apenas a Lei 4.048/2006 isoladamente. Ele precisa identificar também:
* data de ingresso no serviço público; 
* data de ingresso no cargo; 
* tempo de contribuição; 
* tempo de serviço público; 
* tempo na carreira; 
* tempo no cargo; 
* sexo; 
* atividade de professor; 
* eventual direito adquirido; 
* regras de transição constitucionais; 
* situação de incapacidade; 
* atividade especial; 
* eventual enquadramento em regra anterior. 

## 2. Situação atual em 20/08/2026

A Lei Orgânica municipal ainda contém a redação histórica que previa aposentadoria voluntária por tempo de serviço e idade, além da compulsória aos 70 anos. 

Entretanto, em julho de 2026 foi apresentada uma proposta para alterar o art. 87 da Lei Orgânica e adequar o RPPS municipal à EC 103/2019.

A proposta prevê, entre outras mudanças:
* idade mínima de 62 anos para mulher; 
* idade mínima de 65 anos para homem; 
* redução de idade para professores; 
* regras diferenciadas para pessoas com deficiência; 
* regras diferenciadas para atividades insalubres; 
* aposentadoria compulsória aos 75 anos; 
* futura lei complementar para definir cálculo, tempo de contribuição e regras de transição. 

Contudo, a própria tramitação demonstra que se tratava de proposta em processo legislativo, inclusive com questionamento sobre a votação em primeiro turno. 

**Conclusão para o sistema:** essas regras propostas devem ficar fora da apuração da legislação vigente até que exista publicação oficial da alteração e das respectivas leis complementares regulamentadoras.

## 3. Tipos de aposentadoria atualmente relevantes

Para o simulador municipal, eu estruturaria inicialmente os seguintes tipos:

| Tipo | Aplicabilidade |
| --- | --- |
| Aposentadoria voluntária por idade e tempo de contribuição | Sim |
| Aposentadoria voluntária por idade | Sim |
| Aposentadoria compulsória | Sim |
| Aposentadoria por incapacidade permanente | Sim |
| Aposentadoria especial do professor | Sim, como redução da regra de idade/tempo |
| Direito adquirido pelas regras anteriores | Sim |
| Regra de transição EC 41/2003 | Sim, conforme data de ingresso |
| Regra de transição EC 47/2005 | Sim, conforme data de ingresso |
| Regra da EC 70/2012 para incapacidade | Pode ser aplicável conforme data de ingresso e demais requisitos |
| Aposentadoria especial por exposição a agentes prejudiciais | Deve ser analisada separadamente |
| Aposentadoria da pessoa com deficiência | Deve ser analisada conforme legislação aplicável |

A existência de aposentadorias municipais concedidas com fundamento em regras constitucionais anteriores não é apenas teórica. O TCE-MG registra atos do IMP com fundamento, por exemplo, na EC 47/2005 e casos revisionais relacionados à EC 70/2012. 

## 4. Aposentadoria voluntária por idade e tempo de contribuição

Essa é uma das principais regras da Lei nº 4.048/2006.

O art. 32 estabelece:

**Homem**
* 60 anos de idade; 
* 35 anos de contribuição; 
* 10 anos de efetivo exercício no serviço público; 
* 5 anos no cargo efetivo em que ocorrerá a aposentadoria. 

**Mulher**
* 55 anos de idade; 
* 30 anos de contribuição; 
* 10 anos de efetivo exercício no serviço público; 
* 5 anos no cargo efetivo em que ocorrerá a aposentadoria. 

Os requisitos são cumulativos. 

**Professor**
Para professor que comprove exclusivamente tempo de efetivo exercício das funções de magistério na educação infantil e no ensino fundamental e médio, os requisitos de idade e tempo de contribuição são reduzidos em 5 anos.

Portanto:

| Requisito | Homem | Mulher |
| --- | --- | --- |
| Idade normal | 60 | 55 |
| Contribuição normal | 35 | 30 |
| Idade professor | 55 | 50 |
| Contribuição professor | 30 | 25 |
| Serviço público | 10 anos | 10 anos |
| Cargo | 5 anos | 5 anos |

A lei, em seu art. 32, §2º, considera como função de magistério a atividade docente do professor exercida exclusivamente em sala de aula. 

**Ponto importante para o desenvolvimento:** não basta o cargo estar classificado como "Professor". O sistema precisa verificar o tempo efetivamente exercido em função de magistério, conforme a regra legal.

## 5. Aposentadoria voluntária por idade

O art. 33 da Lei 4.048/2006 estabelece a aposentadoria por idade.

Os requisitos básicos são:

**Homem**
* 65 anos de idade; 
* 10 anos de efetivo exercício no serviço público; 
* 5 anos no cargo efetivo. 

**Mulher**
* 60 anos de idade; 
* 10 anos de efetivo exercício no serviço público; 
* 5 anos no cargo efetivo. 

Nesse caso, os proventos são proporcionais ao tempo de contribuição e calculados conforme o art. 59 da Lei 4.048/2006. Isso foi inclusive reconhecido em decisão judicial recente envolvendo servidor efetivo do DAMAE de São João del-Rei. 

Portanto:

| Requisito | Homem | Mulher |
| --- | --- | --- |
| Idade | 65 | 60 |
| Serviço público | 10 anos | 10 anos |
| Cargo | 5 anos | 5 anos |
| Tempo mínimo de contribuição específico | Não indicado no art. 33 | Não indicado no art. 33 |
| Provento | Proporcional | Proporcional |

## 6. Aposentadoria compulsória

O art. 31 da Lei 4.048/2006 determina aposentadoria automática aos:
* 70 anos de idade.

Os proventos são:
* proporcionais ao tempo de contribuição, calculados na forma do art. 59, e não podem ser inferiores ao salário-mínimo.

A aposentadoria passa a vigorar a partir do dia imediatamente seguinte àquele em que o servidor atingir a idade-limite. 

**Atenção: 70 ou 75 anos?**
Esse é um ponto que precisa ficar muito bem controlado no sistema.
A reforma municipal proposta em 2026 pretende elevar a idade compulsória de 70 para 75 anos. 
Enquanto essa alteração não estiver efetivamente incorporada à legislação municipal, o simulador da legislação vigente deve utilizar 70 anos.

## 7. Aposentadoria por incapacidade permanente

A Lei 4.048/2006 também prevê aposentadoria por incapacidade.

Para a simulação, entretanto, essa modalidade não deve ser tratada simplesmente como uma regra de idade/tempo.

O sistema deve receber uma informação proveniente da avaliação médica/previdenciária indicando:
* existência de incapacidade; 
* caráter permanente; 
* impossibilidade de readaptação; 
* data de início da incapacidade; 
* eventual relação com acidente em serviço; 
* eventual relação com moléstia profissional; 
* eventual doença especificada em legislação. 

A Constituição atualmente trata a aposentadoria por incapacidade como benefício decorrente de incapacidade permanente para o trabalho no cargo, quando o servidor for insuscetível de readaptação. 

**Para o simulador**
Eu recomendaria separar:
* Simulação por regras de elegibilidade
* de
* Simulação por incapacidade

porque a segunda depende de uma condição médica/pericial que não pode ser deduzida apenas pela idade e pelo tempo de contribuição.

## 8. Cálculo dos proventos

Esse é um dos pontos mais importantes para o sistema.

A Lei nº 4.048/2006 determina que os proventos das aposentadorias abrangidas pelos arts. 31, 32 e 33 sejam calculados na forma do art. 59. Isso aparece expressamente tanto na regra de aposentadoria compulsória quanto na aposentadoria por idade e na regra de idade + tempo. 

A legislação municipal adota como referência a média aritmética das remunerações utilizadas como base de contribuição. Há inclusive jurisprudência do TJMG reconhecendo que a Lei 4.048/2006 utiliza a média das remunerações de contribuição para cálculo dos proventos. 

Portanto, o simulador precisa manter uma base histórica de remunerações.
Não é suficiente utilizar:
* remuneração atual

O cálculo deve considerar o histórico das remunerações que compõem a base previdenciária.

Sugiro que o sistema tenha, conceitualmente:
Histórico de remunerações de contribuição
↓
Atualização monetária
↓
Seleção das remunerações consideradas
↓
Média
↓
Aplicação da proporcionalidade, quando necessária
↓
Valor estimado do benefício

## 9. Integralidade x média

Essa é uma questão que merece tratamento especial.

O fato de o servidor preencher os requisitos de uma aposentadoria chamada "integral" não significa automaticamente que o benefício será igual à última remuneração.

É necessário identificar qual fundamento constitucional está sendo utilizado.

Existem situações de:
* **Integralidade**: Em determinadas regras anteriores e de transição, especialmente para servidores que ingressaram até determinadas datas, o benefício pode corresponder à remuneração do cargo efetivo.
* **Média**: Nas regras em que o cálculo é pela média, o benefício será obtido a partir das remunerações utilizadas como base de contribuição.

Isso é particularmente importante para as regras de transição das EC 41/2003, EC 47/2005 e outras normas constitucionais.

O TCE-MG continua registrando aposentadorias do IMP com fundamento em regras constitucionais anteriores, inclusive EC 47/2005. 

## 10. Direito adquirido

O simulador precisa obrigatoriamente verificar direito adquirido antes de aplicar as regras atuais.

A ordem conceitual deveria ser:
1. Verificar direito adquirido
2. Verificar regras de transição
3. Verificar regra permanente vigente
4. Verificar aposentadoria compulsória
5. Verificar regras especiais

A própria Lei 4.048/2006 contém disposição assegurando a concessão de aposentadorias para segurados que já haviam cumprido os requisitos até 31/12/2003, de acordo com a legislação então vigente. 

## 11. Regra da EC 41/2003

Para servidores que ingressaram antes da EC 41/2003, devem ser verificadas as regras de transição da própria EC 41.

Uma delas é a regra do art. 6º da EC 41/2003, que exige, em linhas gerais:
* ingresso no serviço público até 31/12/2003; 
* 60 anos de idade para homem; 
* 55 anos para mulher; 
* 35 anos de contribuição para homem; 
* 30 anos para mulher; 
* 20 anos de efetivo serviço público; 
* 10 anos de carreira; 
* 5 anos no cargo. 

Para professor há redução dos requisitos de idade e contribuição, observadas as condições específicas.
Essa regra é particularmente importante para o cálculo com integralidade e paridade, quando presentes os demais requisitos.

## 12. Regra da EC 47/2005

Também deve ser implementada.

A EC 47/2005 estabeleceu uma regra de transição especialmente relevante para servidores que ingressaram no serviço público até 16/12/1998.

O princípio central é a compensação entre:
* idade; 
* tempo de contribuição. 

A regra pode permitir aposentadoria com idade inferior à regra tradicional, desde que o tempo de contribuição seja superior.

O TCE-MG possui caso específico do IMP de São João del-Rei em que foi necessário verificar se a servidora havia ingressado no serviço público antes de 16/12/1998 para demonstrar o direito à regra da EC 47/2005, com proventos integrais. 
Isso demonstra que essa regra não deve ser descartada do simulador municipal.

## 13. EC 70/2012

Também deve ser considerada na aposentadoria por incapacidade.

A EC 70/2012 criou regra específica para servidores que ingressaram no serviço público até 31/12/2003 e posteriormente foram aposentados por invalidez/incapacidade, especialmente quanto à forma de cálculo e à integralidade/paridade nas situações abrangidas.

O TCE-MG possui registros de atos revisionais do próprio IMP de São João del-Rei classificados como "ATO REVISIONAL DE APOSENTADORIA EC 70/2012", demonstrando a aplicação dessa regra no RPPS municipal. 

## 14. Professor

O simulador deve tratar professor como uma característica do tempo, e não simplesmente como um tipo de cargo.

Para a regra do art. 32 da Lei 4.048/2006:
* redução de 5 anos na idade; 
* redução de 5 anos no tempo de contribuição; 
* necessidade de comprovar exclusivamente tempo de efetivo exercício de função de magistério; 
* abrangência da educação infantil, ensino fundamental e ensino médio. 

Isso significa que o sistema deveria conseguir separar:
* Tempo de contribuição total
* Tempo de serviço público
* Tempo no cargo
* Tempo em função de magistério

## 15. Aposentadoria especial

Esse ponto merece uma arquitetura própria.

A Constituição prevê tratamento diferenciado para determinadas situações, incluindo atividades exercidas com efetiva exposição a agentes prejudiciais à saúde.

A Constituição de Minas Gerais, por exemplo, atualmente prevê regra específica para servidor exposto a agentes químicos, físicos e biológicos, mas essa regra é do RPPS estadual, não deve ser simplesmente copiada para o Município. 

Para São João del-Rei, portanto, eu não recomendaria implementar automaticamente a regra estadual no simulador municipal.

O sistema deverá verificar a legislação municipal e constitucional efetivamente aplicável ao servidor municipal e, quando houver lacuna ou necessidade de enquadramento especial, indicar que o cálculo depende de análise previdenciária.

## 16. O que eu recomendo que o simulador calcule

Para cada servidor, o sistema deveria produzir algo semelhante a:

| Regra | Elegível? | Data prevista | Valor estimado | Fundamento |
| --- | --- | --- | --- | --- |
| Direito adquirido | Sim/Não | DD/MM/AAAA | R$ | EC/Lei |
| Idade + tempo | Sim/Não | DD/MM/AAAA | R$ | Lei 4.048/2006 |
| Idade | Sim/Não | DD/MM/AAAA | R$ | Lei 4.048/2006 |
| Professor | Sim/Não | DD/MM/AAAA | R$ | Lei 4.048/2006 |
| EC 41 | Sim/Não | DD/MM/AAAA | R$ | EC 41/2003 |
| EC 47 | Sim/Não | DD/MM/AAAA | R$ | EC 47/2005 |
| EC 70 | Sim/Não | DD/MM/AAAA | R$ | EC 70/2012 |
| Incapacidade | Análise | — | R$ | legislação aplicável |
| Compulsória | Sim/Não | DD/MM/AAAA | R$ | Lei 4.048/2006 |

Eu evitaria apresentar somente:
"Você poderá se aposentar em 2030."

O ideal é apresentar todas as regras para as quais o servidor possui ou poderá adquirir direito, permitindo ao usuário comparar os fundamentos e os valores.

## 17. Dados que o simulador precisará

Para conseguir fazer essa apuração corretamente, eu estruturaria os dados de entrada em pelo menos estes grupos.

**Dados pessoais**
* sexo; 
* data de nascimento; 
* pessoa com deficiência; 
* professor; 
* atividade especial; 
* data de ingresso no serviço público. 

**Dados funcionais**
* data de ingresso no Município; 
* data de ingresso no cargo atual; 
* cargo; 
* carreira; 
* órgão; 
* períodos de afastamento; 
* períodos de suspensão; 
* períodos sem contribuição; 
* períodos de exercício de função de magistério. 

**Dados previdenciários**
* tempo de contribuição no RPPS; 
* tempo de contribuição no RGPS; 
* tempo de contribuição em outros RPPS; 
* períodos averbados; 
* períodos concomitantes; 
* tempo especial; 
* conversões eventualmente reconhecidas; 
* CTCs. 

**Dados financeiros**
* remuneração de contribuição histórica; 
* bases previdenciárias; 
* parcelas incorporáveis; 
* remuneração atual; 
* remuneração do cargo efetivo; 
* histórico de contribuições. 

## 18. Uma questão fundamental: data de elegibilidade

Não recomendo simplesmente armazenar:
`data_aposentadoria`

O cálculo deve determinar a data de cumprimento de cada requisito.

Por exemplo:
* Data de nascimento:       10/05/1970
* Idade mínima:             10/05/2030
* Tempo contribuição:       15/03/2029
* Serviço público:          20/06/2028
* Cargo:                    01/08/2027

A regra somente será cumprida quando todos os requisitos estiverem satisfeitos:
```
MAX(
    data_idade,
    data_contribuicao,
    data_servico_publico,
    data_cargo
)
```

Esse conceito será extremamente importante para evitar erros no simulador.

## 19. Regras de precedência que sugiro

A lógica geral poderia ser:

```
INÍCIO
  ↓
Identificar legislação vigente na data da simulação
  ↓
Verificar direito adquirido
  ↓
Verificar regras de transição
  ↓
Verificar regras permanentes
  ↓
Verificar professor
  ↓
Verificar regras especiais
  ↓
Verificar compulsória
  ↓
Para cada regra elegível:
    calcular data
    calcular base
    calcular provento
    calcular reajuste
  ↓
Apresentar resultados
```

## 20. Alerta importante sobre a reforma de 2026

Esse provavelmente será um dos pontos mais importantes para o desenvolvimento do sistema neste momento.

O IMP atualmente mantém uma página específica sobre a Reforma da Previdência, demonstrando que o assunto está em processo de mudança. 

Além disso, em julho de 2026 a imprensa local informou que o Município apresentou proposta para alterar a Lei Orgânica, criando idade mínima de 62/65 anos e alterando outras regras. 

Portanto, eu recomendo que o módulo seja construído com versionamento de regras previdenciárias, por exemplo:

```sql
REGRA_PREVIDENCIARIA
--------------------
id
descricao
fundamento_legal
data_inicio
data_fim
sexo
idade_minima
tempo_contribuicao
tempo_servico_publico
tempo_carreira
tempo_cargo
tempo_magisterio
forma_calculo
forma_reajuste
paridade
integralidade
ativo
```

Isso permitirá que, quando a reforma municipal for efetivamente publicada, o sistema receba uma nova versão das regras sem precisar alterar toda a lógica de simulação.

## 21. Minha conclusão para a implementação

Com base na legislação que consegui confirmar, o cenário atual de São João del-Rei é significativamente diferente de simplesmente aplicar a EC 103/2019 aos servidores municipais.

Para a versão atual do simulador, a base deve considerar principalmente:
* Lei Municipal nº 4.048/2006
* aposentadoria compulsória aos 70 anos; 
* aposentadoria voluntária por idade + tempo; 
* aposentadoria voluntária por idade; 
* redução de 5 anos para professor na regra do art. 32; 
* aposentadoria por incapacidade; 
* cálculo conforme art. 59; 
* regras constitucionais anteriores preservadas; 
* direito adquirido; 
* regras de transição das EC 41/2003 e EC 47/2005; 
* EC 70/2012 nas situações de incapacidade; 
* demais situações especiais conforme enquadramento legal. 

O Estatuto Municipal nº 5.038/2014 confirma que o benefício dos efetivos/estáveis é concedido pelo IMP conforme a Constituição e suas Emendas. 

E há evidência concreta no TCE-MG de que o IMP de São João del-Rei continua concedendo/registrando benefícios fundamentados em regras constitucionais de transição, inclusive EC 47/2005 e EC 70/2012. 

**Atenção:** eu não implementaria ainda no simulador as regras da reforma de 2026 — 62/65 anos, compulsória aos 75, nova fórmula de cálculo etc. — como regras vigentes. Elas devem ser tratadas como legislação futura/proposta até que sejam efetivamente promulgadas e regulamentadas. 

### Fontes oficiais/prioritárias encontradas
* Lei Municipal nº 4.048/2006 — IMP São João del-Rei 
* Lei Ordinária nº 4.048/2006 — Câmara Municipal 
* IMP — Instituto Municipal de Previdência de São João del-Rei 
* TCE-MG — caso de aposentadoria do IMP envolvendo EC 47/2005 
* TJMG — aposentadoria por idade estatutária segundo a Lei 4.048/2006 

Próximo passo que considero mais útil para o seu projeto: transformar essa pesquisa em uma especificação funcional completa do simulador de aposentadoria, detalhando cada regra em formato de requisitos de programação, com as fórmulas para data de elegibilidade, tempo de contribuição, integralidade/média, proporcionalidade, paridade, professor, EC 41, EC 47, EC 70 e direito adquirido, além de uma matriz de decisão para o programador implementar no sistema.
