<template>
  <q-page class="q-pa-md" style="background-color: #ebebeb;">
    <q-tabs
    v-model ="tab"
    align
    inline-label
    class="bg-white text-while shadow2">
      <q-tab name="carrinho" label="Carrinho"/>
      <q-tab name="armazem"  label="Armazem"/>
      <q-tab name="nfc"      label="NFC"/>
    </q-tabs>
    <q-separator/>
    <q-tab-panels v-model="tab" animated class="q-pa-none" style="background-color: #ebebeb;">
      <q-tab-panel name="carrinho" class="q-pa-none" >
          <div class="row">
            <div class="col-8 fundo1" >
              <q-table
              flat bordered
              :columns="colunas"
              row-key="name"
              >


                <!--<q-list>


                  <q-item clickable v-ripple v-for="data in itens">
                    <q-item-section avatar>
                      <q-avatar>
                        <img :src="data.imagem">
                      </q-avatar>
                    </q-item-section>
                    <q-item-section>{{data.name}}</q-item-section>
                    <input type="text" maxlength="4" size="10" placeholder="0">
                  </q-item>



                </q-list>-->
              </q-table>
            </div>
            <div class="col-4" >
              <div class="espaco extension">
                <div class="my-card q-pa-lg">
                  <q-btn
                    round
                    color="white"
                    class="logo"
                  >
                  <q-avatar size="150px">
                    <img src="https://storage.googleapis.com/stateless-novovinteconto-com-b/2023/02/ee6aff76-logotipo-personalizado-mesa.png">
                  </q-avatar>
                  </q-btn>
                </div>

                <div class="my-card q-pa-md" style="min-height: 500px;background-color: white;">

                  <div class="resumo">
                    <label name="resumoC">Resumo da Compra</label>


                    <div class="valores">
                      <label name="sub">SubTotal</label>
                      <input id="sub" name="valorSub" type="text" placeholder="000,00">
                    </div>
                    <div class="valores">
                      <label name="desconto">Desconto</label>
                      <input id="desc" name="valorDesc" type="text" placeholder="000,00">
                    </div>
                    <div class="valores">
                      <label name="total">Total</label>
                      <input id="total" name="valorTotal" type="text" placeholder="000,00">
                    </div>
                    <div class="valores">
                      <label name="pay">Pago</label>
                      <input id="pay" name="valorPay" type="text" placeholder="000,00">
                    </div>
                    <div class="valores">
                      <label name="exc">Troco</label>
                      <input id="exc" name="valorExchange" type="text" placeholder="000,00">
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

            <div class="fundo1 q-pa-md sep">
                <q-toolbar class="text-white q-pa-none">
                  <q-toolbar-title>
                    <q-btn
                      class="btnBot"
                      style="background-color: #3583DB;"
                      label="Adicionar Produto"
                      no-caps />
                  </q-toolbar-title>
                  <div>
                    <q-btn
                    class="btnBot"
                    style="background-color: #E8361E;"
                    label="Remover Produto"
                    no-caps />
                    <q-btn
                    class="btnBot espaco"
                    style="background-color: #5db839;"
                    label="Finalizar Carrinho"
                    no-caps />
                  </div>
                </q-toolbar>
            </div>

      </q-tab-panel>
    </q-tab-panels>
  </q-page>
</template>

<script setup>
import {ref} from 'vue'
  const tab = ref('carrinho')
  const clicou = () =>{
    console.log('clicou')
  }
  const itens = [
    {
      name: 'nome1',
      imagem: 'https://images.tcdn.com.br/img/img_prod/751108/sacola_de_papel_preta_18x24x10_50_unidades_125_1_4129afe3ca4ea8000ee0e2a62f3fc6ff.png'
    },
    {
      name: 'mulher',
      imagem: 'https://static.vecteezy.com/ti/vetor-gratis/p3/350131-icone-de-pacote-de-gratis-vetor.jpg'
    }
  ]
  const colunas=[
    {
      name: 'quantidade',
      required: true,
      align: 'left',
      label: 'Quantidade',
    },
    { name:'produto', align:'left', label:'Produto', required: true },
    { name:'unit', align:'right', label:'Unidades', required: true }

  ]
</script>

<style>
  .fundo1{
    background-color:white;
    color: black
    /*green #5db839*/
  }
  .espaco{
    margin-left: 15px;
  }
  .extension{
    min-height:700px;
  }
  .logo{
    margin: auto;
    display:grid;
  }

  /*Caixa Valores Venda*/
  .valores{
    display:flex;
    flex-direction: column;
    margin-top:1.1rem;
  }
  .valores input{
    margin:0.1rem 0;
    padding: 0.7rem 1.1rem;
    border-radius: 5px;
    border-style:solid;
    border: none;
    background-color: #ebebeb;
    box-shadow: 0.5px 0.5px #000000;
  }
  /*.valores input:hover{
    background-color: #eeeeee75;
  }*/
  .valores label{
    font-size: 0.80rem;
  }
  .resumo{
    font-size: 1rem;
    font-family: arial;
  }
  .botBox{
    margin-top: 15px;
    min-height:75px;
  }

  .btnBot{
    padding-top: 0.5rem ;
    padding-bottom: 0.5rem;
    font-size: 20px;
    font-family: arial;
  }
  .sep{
    margin-top:10px;
  }
</style>
