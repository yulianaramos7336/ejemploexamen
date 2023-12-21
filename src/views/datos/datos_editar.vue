<template>
    <div class="row">
        <div class="col-md-12">
            <div class="card">
                <div class="card-body">
                    <div class="mb-3">
                        <label class="form-label">nombres</label>
                        <input v-model="datos.nombres" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">calle</label>
                        <input v-model="datos.calle" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">numero</label>
                        <input v-model="datos.numero" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">colonia</label>
                        <input v-model="datos.colonia" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">municipio</label>
                        <input v-model="datos.municipio" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">codigo</label>
                        <input v-model="datos.codigo" type="email" class="form-control">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">telefono</label>
                        <input v-model="datos.telefono" type="email" class="form-control">
                    </div>
                </div>
            </div>
        </div>
        <div class="col-md-12">
            <button @click="guardar()" type="button" class="btn btn-primary">Guardar</button>
            <RouterLink class="btn btn-light" to="/datos_listar">Cancelar</RouterLink>
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
            datos: {
                nombres: '',
                calle: '',
                Numero: '',
                colonia: '',
                municipio: '',
                codigo: '',
                telefono: '',
                email: '',
                calle: '',
                Numero: '',
                colonia: '',
                municipio: '',
                codigo: '',
                telefono: '',
                email: '',
                escritura: '',
                volumen: '',
                notaria: '',
                localidad: '',
            },
        }
    },
    methods: {
        async getUrls() {
            try {
                const q = doc(db, "datos", this.id);
                const respuesta = await getDoc(q);
                this.datos=respuesta.data()
            } catch (error) {
                console.log(error);
            }
        },
        async guardar() {
            try {
                const q = doc(db, 'datos',this.id);
                const docRef = await updateDoc(q,this.datos);
                this.$router.push({ name: 'datos_listar' })
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