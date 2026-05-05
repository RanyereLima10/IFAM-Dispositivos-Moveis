
⚠️ Atenção, alunos:
Por favor, Não anexar arquivos ou textos diretamente aqui.
A atividade deve ser entregue exclusivamente pelo GitHub, conforme as instruções fornecidas (pasta individual ou grupo)


⚠️ Atenção, alunos:IMPORTANTE: Todo o código deve ser comentado linha por linha, explicando de forma clara o que cada parte do código faz. Códigos sem comentários não serão totalmente considerados na avaliação.


⚠️ Atenção, alunos:
Segue um modelo de cabeçalho padrão já organizado + uma mensagem clara (pronto para copiar e usar nas atividades e grupos):

/**********************************************************************/

INSTITUTO FEDERAL DO AMAZONAS – IFAM CAMPUS IRANDUBA  
DISCIPLINA: Dispositivos Móveis  
PROFESSOR: Ranyere Lima  
ALUNO(A): __________________________________________  
DATA: ____ / ____ / 2026  
BIMESTRE: 2º Bimestre  

DESCRIÇÃO DA ATIVIDADE:  
Nesta atividade, o(a) aluno(a) deverá desenvolver uma aplicação mobile simples utilizando React Native, com o objetivo de compreender a estrutura básica de um aplicativo.
O projeto deve conter uma tela inicial com uma mensagem de boas-vindas e pelo menos um botão interativo. Ao interagir com o botão, o aplicativo deve apresentar uma resposta na tela (ex: alerta, mudança de texto ou ação visual).
Também devem ser aplicados conceitos de estilização utilizando StyleSheet, permitindo a personalização de cores, tamanhos e organização dos elementos.
A atividade tem como objetivo reforçar o uso de componentes fundamentais como View, Text, Button e Alert, além de desenvolver a lógica de programação e organização do código. 

/**********************************************************************/


/**********************************************************************/
 ****⚠️ Atenção, EXEMPLO: Componente React – Data com rolagem *********
/**********************************************************************/

import React, { useState } from "react";

export default function DataPicker() {
  const anoAtual = new Date().getFullYear();

  const dias = Array.from({ length: 30 }, (_, i) => i + 1);
  const meses = Array.from({ length: 12 }, (_, i) => i + 1);
  const anos = Array.from({ length: anoAtual - 1970 + 1 }, (_, i) => 1970 + i);

  const [dia, setDia] = useState(1);
  const [mes, setMes] = useState(1);
  const [ano, setAno] = useState(anoAtual);

  return (
    <div style={styles.container}>
      <h2>Selecionar Data</h2>

      <div style={styles.pickerContainer}>
        {/* DIA */}
        <select value={dia} onChange={(e) => setDia(e.target.value)} style={styles.select}>
          {dias.map((d) => (
            <option key={d} value={d}>
              {d}
            </option>
          ))}
        </select>

        {/* MÊS */}
        <select value={mes} onChange={(e) => setMes(e.target.value)} style={styles.select}>
          {meses.map((m) => (
            <option key={m} value={m}>
              {m}
            </option>
          ))}
        </select>

        {/* ANO */}
        <select value={ano} onChange={(e) => setAno(e.target.value)} style={styles.select}>
          {anos.map((a) => (
            <option key={a} value={a}>
              {a}
            </option>
          ))}
        </select>
      </div>

      <p style={styles.resultado}>
        Data selecionada: {dia}/{mes}/{ano}
      </p>
    </div>
  );
}

const styles = {
  container: {
    textAlign: "center",
    marginTop: "50px",
    fontFamily: "Arial",
  },
  pickerContainer: {
    display: "flex",
    justifyContent: "center",
    gap: "10px",
    marginTop: "20px",
  },
  select: {
    padding: "10px",
    fontSize: "16px",
    borderRadius: "8px",
  },
  resultado: {
    marginTop: "20px",
    fontSize: "18px",
  },
};

/**********************************************************************/
 ******** FIM EXEMPLO: Componente React – Data com rolagem ************
/**********************************************************************/
