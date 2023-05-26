<template>
    <teleport to="body">
        <base-dialog v-if="inputIsInvalid" :title="'Invalid input'" @close="closeModal">
            <template #default>
                <p>Lo siento, al menos uno de los valores son invalidos</p>
                <p>Porfavor revisa los valores y asegurate de ingresarlos todos</p>
            </template>
            <template #actions>
                <base-button @click="closeModal">Ok</base-button>
            </template>
        </base-dialog>
    </teleport>
    <base-card>
    <form @submit.prevent="submitData">
        <div class="form-control">
            <label for="title">Titulo</label>
            <input id="title" name="title" type="text" ref="titleInput">
        </div>
        <div class="form-control">
            <label for="description">Descripcion</label>
            <textarea name="description" id="description" rows="3" ref="descInput"></textarea>
        </div>
        <div class="form-control">
            <label for="link">Link</label>
            <input id="link" name="link" type="text" ref="linkInput">
        </div>
        <div>
            <base-button type="submit">Añadir Recurso</base-button>
        </div>
    </form>
    </base-card>
</template>

<script>

export default{
    inject:['addRe'],
    data(){
        return{
            inputIsInvalid: false
        }
    },
    methods:{
        submitData(){
            const enteredTitle = this.$refs.titleInput.value;
            const enteredDesc = this.$refs.descInput.value;
            const enteredLink = this.$refs.linkInput.value;

            if(enteredTitle.trim() === '' || enteredDesc.trim() === '' || enteredLink.trim() === ''){
                this.inputIsInvalid = true;
                return;
            }

            this.addRe(enteredTitle, enteredDesc, enteredLink);
        },
        closeModal(){
            this.inputIsInvalid = false;
        }
    }
}

</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>