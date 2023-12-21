<template>
    <div class="row">
        <div class="col-md-12">
            <RouterLink class="btn btn-primary" to="/datos_crear">agragar datos generales</RouterLink>
        </div>
        <div class="col-md-12">
            <div class="card">
                <div class="card-body">
                    <table class="table">
                        <thead>
                            <tr>
                                <th scope="col">codigo</th>
                                <th scope="col">colonia</th>
                                <th scope="col">telefono</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="data in datos">
                                <td>{{ data.codigo }}</td>
                                <td>{{ data.colonia }}</td>
                                <td>{{ data.telefono }}</td>
                                <td>
                                    <RouterLink class="btn btn-success" :to="'/datos_editar/' + data.id">Editar</RouterLink>
                                    <button class="btn btn-danger" @click="eliminar(data.id)">Eliminar
                                    </button>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import { collection, getDocs, query, where,deleteDoc,doc } from "firebase/firestore";
import { auth, db } from "../../firebaseConfig";

import { defineComponent } from 'vue';
export default defineComponent({
    data() {
        return {
            loadingDoc: false,
            datos: []
        }
    },

    methods: {
        async getUrls() {
            try {
                this.datos= []
                const q = query(
                    collection(db, "datos")
                );
                const querySnapshot = await getDocs(q);
                querySnapshot.forEach((doc) => {
                    // console.log(doc.id);
                    this.datos.push({
                        codigo: doc.data().codigo,
                        colonia: doc.data().colonia,
                        telefono: doc.data().telefono,
                        id: doc.id,
                        // ...doc.data()
                    });
                });
                // console.log(this.datos);
            } catch (error) {
                console.log(error);
            }
        },
        async eliminar(id) {
            try {
                const q = doc(db, "datos", id);
                const docRef = await deleteDoc(q);
                this.getUrls()
            } catch (error) {
                console.log(error);
            }
        },
    },
    mounted() {
        this.getUrls()
    }
})
</script>