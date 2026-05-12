
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




/**********************************************************************/
 ****⚠️ Atenção, Exemplo de Layout Responsivo no Snack ***************
/**********************************************************************/

import React from 'react';
import {
  View,
  Text,
  StyleSheet,
  Dimensions,
  ScrollView
} from 'react-native';

const larguraTela = Dimensions.get('window').width;

export default function App() {

  return (

    <ScrollView contentContainerStyle={styles.container}>

      <Text style={styles.titulo}>
        Layout Responsivo
      </Text>

      <View style={styles.cardContainer}>

        <View style={styles.card}>
          <Text style={styles.textoCard}>HTML</Text>
        </View>

        <View style={styles.card}>
          <Text style={styles.textoCard}>CSS</Text>
        </View>

        <View style={styles.card}>
          <Text style={styles.textoCard}>JavaScript</Text>
        </View>

        <View style={styles.card}>
          <Text style={styles.textoCard}>React Native</Text>
        </View>

      </View>

    </ScrollView>

  );

}

const styles = StyleSheet.create({

  container: {
    flexGrow: 1,
    backgroundColor: '#EAF2FF',
    alignItems: 'center',
    padding: 20
  },

  titulo: {
    fontSize: 28,
    fontWeight: 'bold',
    marginBottom: 20
  },

  cardContainer: {

    flexDirection: 'row',

    flexWrap: 'wrap',

    justifyContent: 'center'

  },

  card: {

    width: larguraTela * 0.4,

    height: 120,

    backgroundColor: '#4A90E2',

    margin: 10,

    borderRadius: 15,

    justifyContent: 'center',

    alignItems: 'center'

  },

  textoCard: {
    color: 'white',
    fontSize: 18,
    fontWeight: 'bold'
  }

});

/**********************************************************************/
 ******** FIM Exemplo de Layout Responsivo no Snack********************
/**********************************************************************/








