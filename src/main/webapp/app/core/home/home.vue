<template>
  <div class="home row">
    <div class="col-md-9">
      <h1 class="display-4" v-text="$t('home.title')">Welcome on our shop !</h1>

      <div class="topnav">
        <input type="text" placeholder="Search.." size=100>
      </div>

      <button id="search-button" type="button">Search..</button>

      <div>
        <div class="alert alert-success" v-if="authenticated">
          <span v-if="username" v-text="$t('home.logged.message', { username: username })">You are logged in as user "{{ username }}"</span>
        </div>

        <div class="alert alert-warning" v-if="!authenticated">
          <span v-text="$t('global.messages.info.authenticated.prefix')">If you want to </span>
          <a class="alert-link" v-on:click="openLogin()" v-text="$t('global.messages.info.authenticated.link')">sign in</a
          ><span v-html="$t('global.messages.info.authenticated.suffix')"
            >, you can try the default accounts:<br />- Administrator (login="admin" and password="admin") <br />- User (login="user" and
            password="user").</span
          >
        </div>
        <div class="alert alert-warning" v-if="!authenticated">
          <span v-text="$t('global.messages.info.register.noaccount')">You don't have an account yet?</span>&nbsp;
          <router-link class="alert-link" to="/register" v-text="$t('global.messages.info.register.link')"
            >Register a new account</router-link
          >
        </div>
      </div>

      <div id="my-div" text-align = center>
	  <a href="http://localhost:9000/ItemDetails">
	  <p class="text">test</p>
	  <img src="../../../content/images/logo-jhipster.png" /></a>
	</div>

    </div>
  </div>
</template>

<style>
	#my-div {
		text-align : center;
	}
	
	#search-button {
	position: absolute;
	top: 75px; left: 800px;
	}
	</style>

<script lang="ts" src="./home.component.ts"></script>
