<template>
    <div class="row justify-content-center">
        <div class="col-md-6">

            <h3 class="text-center">¿Qué es la Evaluación 360º?</h3>
            <br>
            <p>
            La Evaluación 360º permite evaluar al personal de una manera más completa y con una 
            óptica general. Anteriormente un cargo era evaluado por un superior, pero esto no 
            permite resultados objetivos y concluyentes.
            </p>

            <p>
            El Sistema de Evaluación 360º logra mejorar esta labor, convirtiéndose en la 
            herramienta que ayuda para el desarrollo del Talento Humano de su 
            Empresa.
            </p>
            
            <img src="../Sistema_de_evaluacion_360.jpg" 
            width="541" height="434"
            alt="Sistema_360º" >
            
            <br><br><br>

            <h3 class="text-center">Crear Evaluación</h3>
            <form @submit.prevent="handleSubmitForm">
                <div class="form-group">
                    <label>Nombre</label>
                    <input
                        type="text"
                        class="form-control"
                        v-model="student.name"
                        required
                    />
                </div>
                
                <div class="form-group">
                    <label>Identificación</label>
                    <input
                        type="email"
                        class="form-control"
                        v-model="student.email"
                        required
                    />
                </div>
                
                <div class="form-group">
                    <label>Evaluación</label>
                    <input
                        type="text"
                        class="form-control"
                        v-model="student.phone"
                        required
                    />
                </div>

                <div class="form-group">
                    <button class="btn btn-danger btn-block">Crear</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    data() {
        return {
            student: {
                nombre: "",
                identificacion: "",
                evaluacion: "",
            },
        };
    },
    methods: {
       handleSubmitForm() { 
           let apiURL = "http://localhost:4000/api/create-student"; 
           
           axios 
            .post(apiURL, this.student) 
            .then(() => { 
                this.$router.push("/view"); 
                this.student = { 
                    name: "", 
                    email: "", 
                    phone: "", 
                }; 
            })
            .catch((error) => { 
                console.log(error); 
            }); 
        }, 
    }, 
}; 
</script>  