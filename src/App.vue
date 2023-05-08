<script setup>
import { ref, computed } from 'vue'
const nome = ref('')
const email = ref('')
const senha = ref('')
const confirmacao = ref('')
const data = ref('')
const endereco = ref('')
const cidade = ref('')
const estado = ref('')
const hobbie = ref('')
const programacao = ref('')
const biografia = ref('')
const ok = ref(false)

function validar(){
  if (senha.value === confirmacao.value) {
    return true;
  }
  else{
    return false;
  }
}
const mensagemErro = computed(() => {
  if(senha.value != confirmacao.value){
    return 'As senhas devem ser iguais'
  } else{
    return ''
  }
})

</script>
<template>
  <form @submit.prevent= "ok = validar()">
  <div>
    <p>
    <button>Nome:</button>
    <input type="text" v-on:keypress="ok=false" v-model="nome" placeholder="Digite seu nome" />
    </p>

    <p>
    <button>Email:</button>
    <input type="email" v-on:keypress="ok=false" v-model="email" placeholder="Digite seu email" />
    </p>

    <p>
    <button>Senha:</button>
    <input type="password" v-on:keypress="ok=false" v-model="senha" placeholder="Digite sua senha" maxlength="20"/>
    </p>

    <p>
    <button>Confirmação de senha:</button>
    <input type="password" v-on:keypress="ok=false" v-model="confirmacao" placeholder="Digite sua senha novamente" maxlength="20"/>
    </p>

    <p>
    <button>Data de nascimento:</button>
    <input type="date" v-on:keypress="ok=false" v-model="data" placeholder="Digite sua data" />
    </p>

    <p>
    <button>Endereço:</button>
    <input type="text" v-on:keypress="ok=false" v-model="endereco" placeholder="Digite seu endereço" />
    </p>

    <p>
    <button>Cidade:</button>
    <input type="text" v-on:keypress="ok=false" v-model="cidade" placeholder="Digite sua cidade" />
    </p>
    
    <p>
    <label for="estado" >Estado:</label>
    <select v-on:keypress="ok=false" v-model="estado">
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapá</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceará</option>
      <option value="DF">Distrito Federal</option>
      <option value="ES">Espírito Santo</option>
      <option value="GO">Goías</option>
      <option value="MA">Maranhão</option>
      <option value="MT">Mato Grosso</option>
      <option value="MS">Mato Grosso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Pará</option>
      <option value="PB">Paraíba</option>
      <option value="PE">Pernambuco</option>
      <option value="PI">Piauí</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande do Norte</option>
      <option value="RS">Rio Grande do Sul</option>
      <option value="RO">Rondônia</option>
      <option value="RR">Roráima</option>
      <option value="SC">Santa Catarina</option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
     </select>
    </p>
  
    <p>
    <button>Hobbie:</button>
    <input type="text" v-on:keypress="ok=false" v-model="hobbie" placeholder="Digite seu hobbie" />
    </p>

    <p>
    <button>Linguagem de programação:</button>
    <input type="text" v-on:keypress="ok=false" v-model="programacao" placeholder="Digite sua linguagem de programação" />
    </p>
    
    <p>
    <button>Biografia:</button>
    <input type="text" v-on:keypress="ok=false" v-model="biografia" placeholder="Digite sua biografia" />
    </p>
  
    <button @click="ok = !ok">Mostrar</button>
    <p>{{ mensagemErro }}</p>
  </div>
    </form>
  <div v-if="ok">
    <p>O nome digitado é: {{ nome }}</p>
    <p>O email digitado é: {{ email }}</p>
    <p>A senha digitada é: {{ senha }}</p>
    <p>A confirmação digitada é: {{ confirmacao }}</p> 
    <p>A data digitada é: {{ data }}</p>
    <p>O endereço digitado é: {{ endereco }}</p>
    <p>A cidade digitada é: {{ cidade }}</p>
    <p>O estado digitado é: {{ estado }}</p>
    <p>O hobbie digitado é: {{ hobbie }}</p>
    <p>A linguagem de programação digitada é: {{ programacao }}</p>
    <p>A biografia digitada é: {{ biografia }}</p>
  </div>
</template>

<style scoped>

button {
  margin: 5px;
  font-weight: bold;
  width: 200px;
  background-color: rgb(50, 177, 209);
  color: rgb(248, 248, 248);

}

label {
  margin: 50px;
  font-weight: bold;
  background-color: rgb(50, 177, 209);
  color: rgb(248, 248, 248);

}

select{
  background-color: rgb(50, 177, 209);
  font-weight: bold;
}

form {
  width: 25%;
  margin: 5em auto;
  padding: 3em;
  background-color:rgb(153, 240, 240);
  animation-name: nova_animacao;
  animation-duration: 2s;
  animation-delay: 0s;
  animation-direction: alternate;
  animation-iteration-count: infinite;

}
@keyframes nova_animacao {
   50% {background-color:rgb(153, 240, 240);;}
   50% {background-color:#26dfe6;}
  
}


</style>