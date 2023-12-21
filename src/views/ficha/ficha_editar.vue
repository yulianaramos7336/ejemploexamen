<template>
    <div class="row">
        <div class="col-md-12">
            <div class="card">
                <div class="card-body">
                    <div class="mb-3">
                        <label class="form-label">Ingresar apellido</label>
                        <input v-model="ficha.apellido" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">nombre</label>
                        <input v-model="ficha.nombre" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">CMP</label>
                        <input v-model="ficha.cmp" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">RNE</label>
                        <input v-model="ficha.rne" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">DNI/CIP</label>
                        <input v-model="ficha.dni" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Profesion</label>
                        <input v-model="ficha.profesion" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Domicilio</label>
                        <input v-model="ficha.domicilio" type="email" class="form-control">
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-12">
            <button @click="guardar()" type="button" class="btn btn-primary">Guardar</button>
            <RouterLink class="btn btn-light" to="/ficha_listar">Cancelar</RouterLink>
        </div>
    </div>
</template>
<script>

import { collection, getDocs,getDoc, query, where, addDoc, updateDoc, doc } from "firebase/firestore";
import { auth, db } from "../../firebaseConfig";
import { defineComponent } from 'vue';
export default defineComponent({
    data() {
        return {
            id: this.$route.params.id,
            ficha: {
                apellido: '',
                nombre: '',
                cmp: '',
                rne: '',
                dni: '',
                profesion: '',
                domicilio: '',
            },
        }
    },
    methods: {
        async getUrls() {
            try {
                const q = doc(db, "ficha", this.id);
                const respuesta = await getDoc(q);
                this.ficha=respuesta.data()
            } catch (error) {
                console.log(error);
            }
        },
        async guardar() {
            try {
                const q = doc(db, 'ficha',this.id);
                const docRef = await updateDoc(q,this.ficha);
                this.$router.push({ name: 'ficha_listar' })
            } catch (error) {
                console.log(error);
            }
        },
    },
    created() {
        this.getUrls()
    }
})
</script>