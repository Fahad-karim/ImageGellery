<template>
	<div class="ui secondary pointing menu">
		<router-link to="/" class="active item">Image Storage</router-link>

		<div class="right menu">
			<div  v-if="isLoggedIn" class="horizontal">
				<router-link to="/" class="item" >Galleries</router-link>
				<router-link to="/upload" class="item">upload</router-link>
				<a class="item" href="" @click="logout">logout</a>
			</div>
			<a v-else href="#" class="ui item" @click="login">
				login
			</a>
		</div>
	</div>
</template>


<script>
import {mapActions, mapGetters} from 'vuex';
	export default{
		name:'AppHeader',
		computed:mapGetters(['isLoggedIn']),
		methods: mapActions(['login','logout'])
	};
</script>

<style type="text/css">
	.horizontal{
		display: flex;
		flex-direction: row;
	}
</style>