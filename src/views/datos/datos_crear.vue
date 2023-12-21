<template>
    <div class="row">
        <div class="col-md-12">
            <div class="card">
                <div class="card-body">
                    <h1 class="text-center" style="color: aqua;">Datos Generales De La Persona</h1>
                    <div class="mb-3">
                        <label class="form-label">Nombres</label>
                        <input v-model="datos.nombres" type="text" class="form-control">
                    </div>
                    <h2 class="text-center" style="color: aquamarine;">NOMBRE DE LA PERSONA(FISICA O MORAL)</h2>
                    <h3 style="color: blue;">1. DOMICILIO FISCAL</h3>
                    <div class="row">
                        <div class="col-md-6">
                            <div class="mb-3">
                                <label class="form-label">Calle</label>
                                <input v-model="datos.calle" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-6">
                            <div class="mb-3">
                                <label class="form-label"> Numero EXT/INT</label>
                                <input v-model="datos.Numero" type="text" class="form-control">
                            </div>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-6">
                            <div class="mb-3">
                                <label class="form-label">Colonia</label>
                                <input v-model="datos.colonia" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-6">
                            <div class="mb-3">
                                <label class="form-label">Municipio</label>
                                <input v-model="datos.municipio" type="text" class="form-control">
                            </div>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">codigo postal</label>
                                <input v-model="datos.codigo" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">telefono</label>
                                <input v-model="datos.telefono" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">fax</label>
                                <input v-model="datos.fax" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">E-mail</label>
                                 <input v-model="datos.email" type="text" class="form-control">
                            </div>
                        </div>
                    </div>
                    <h4>En caso de tener un domicilio de oficinas centrales distintos al domicilio fiscal</h4>
                    <h5 style="color: blue;"> OFICINA CENTRAL</h5>
                    <div class="row">
                        <div class="col-md-6">
                            <div class="mb-3">
                                <label class="form-label">Calle</label>
                                <input v-model="datos.calle" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-6">
                            <div class="mb-3">
                                <label class="form-label"> Numero EXT/INT</label>
                                <input v-model="datos.Numero" type="text" class="form-control">
                            </div>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-12">
                            <div class="mb-3">
                                <label class="form-label">Colonia</label>
                                <input v-model="datos.colonia" type="text" class="form-control">
                            </div>
                            <div class="mb-3">
                                <label class="form-label">Municipio</label>
                                <input v-model="datos.municipio" type="text" class="form-control">
                            </div>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">codigo postal</label>
                                <input v-model="datos.codigo" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">telefono</label>
                                <input v-model="datos.telefono" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">fax</label>
                                <input v-model="datos.fax" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">E-mail</label>
                                 <input v-model="datos.email" type="text" class="form-control">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-body">
                       <h1>En caso de persona moral</h1>
                       <h2 style="color: blue;">2. CONSTITUTIVAS</h2>
                       <div class="row">
                        <div class="col-md-2">
                            <div class="mb-3">
                                <label class="form-label">No de escritura</label>
                                <input v-model="datos.escritura" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">volumen</label>
                                <input v-model="datos.volumen" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="mb-3">
                                <label class="form-label">notaria no</label>
                                <input v-model="datos.notaria" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-3">
                            <div class="mb-3">
                                <label class="form-label">notario</label>
                                 <input v-model="datos.notario" type="text" class="form-control">
                            </div>
                        </div>
                        <div class="col-md-2">
                            <div class="mb-3">
                                <label class="form-label">localidad</label>
                                 <input v-model="datos.localidad" type="text" class="form-control">
                            </div>
                        </div>
                    </div>
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

import { collection, getDocs, query, where,addDoc } from "firebase/firestore";
import { auth, db } from "../../firebaseConfig";
import { defineComponent } from 'vue';
export default defineComponent({
    // name: 'scanner',
    data() {
        return {
            loadingDoc: false,
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
        async guardar() {
            try {
                const q = query(collection(db, 'datos'));
                const docRef = await addDoc(q, this.datos);
                this.$router.push({ name: 'datos_listar' })
            } catch (error) {
                console.log(error);
            } 
        },
    },
    created() {
    }
})
</script>