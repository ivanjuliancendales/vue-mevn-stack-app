<template>
  <div>
    <!-- Nav bar -->
    <nav
      class="navbar navbar-dark bg-dark justify-content-between flex-nowrap flex-row"
    >
      <div class="container">
        <a class="navbar-brand float-left">Sistema de Evaluación 360º</a>
        <ul class="nav navbar-nav flex-row float-right">
          <li class="nav-item col-md-5">
            <router-link class="nav-link pr-3" to="/"
              >Ingrese evaluación</router-link
            >
          </li>
          <li class="nav-item col-md-5">
            <router-link class="nav-link" to="/view">Visualice evaluaciones</router-link>
          </li>
        </ul>

        <button class="btn btn-success navbar-btn">Contacto</button>

      </div>
    </nav>
    <!-- Router view -->
    <div class="container mt-5">
      <router-view></router-view>
    </div>
  </div>
</template>
