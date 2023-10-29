/* <template>
<v-app-bar color="primary" app>
	<v-list-item-avatar><v-icon @click.stop="showMenu()" large>mdi-menu</v-icon></v-list-item-avatar>
	<div class="text-center">
	</div>
	/* <template >
			<div >
			<v-avatar :size="35">
				<img  src="@/assets/global.png"/>
			</v-avatar>
			<select
			class="mx-2"
			v-model="$i18n.locale"
			@change="updateLanguage($event.target.value)"
			variant="info">
			<v-icon>mdi-chevron-down</v-icon>
			<option
			hide-details
			v-for="(o, i) in locales_array"
			:key="i"
			:value="o.value"
			:selected="o.value === locale_default"
			> {{ o.caption }}
			</option>
			</select>
			</div>
			<v-spacer></v-spacer>
			<v-list>
				<v-list-item @click="listenLogout()">
				<v-list-item-title>
					Cerrar Sesión
				</v-list-item-title>
				</v-list-item>
			</v-list>
		</template>
</v-app-bar>
</template>
/* <script lang="ts">
	import { Component, Vue, Prop } from 'vue-property-decorator';
	import { LOCALES, Locales } from "@/locales/i18n";
	import MixinLogin from '@/mixing/MixinLogin.vue';
	import defaultLocale from "@/i18n";
	@Component({
		name: 'AppBar',
	})
	
	export default class AppBar extends MixinLogin {
		public locales_array = LOCALES;
		public locale_default = defaultLocale;
		@Prop() readonly keycloak!: string

		public listenLogout() {
            this.logout(); ///despúes podría volver a comentar esto
            Util.showMessage('Hasta pronto', Icon.INFO);///despúes podría volver a comentar esto
            this.$router.push({
                name: 'Login',
            });
            this.keycloak.logout(); ///despúes podría volver a comentar esto
        }
		public updateLanguage(lang: Locales) {
			console.log("cambiando idioma a ", lang);
			this.$emit('changeEvent', lang);
		}

		public showMenu() {
            this.$root.$refs.compmenu_component.showMenu2();
        }

	}
</script>
*/
<template>
	<v-app-bar color="primary" app>
	  <v-list-item-avatar>
		<v-icon @click.stop="showMenu">mdi-menu</v-icon>
	  </v-list-item-avatar>
	  <div class="text-center">
		<v-avatar :size="35">
		  <img src="@/assets/global.png" />
		</v-avatar>
		<select class="mx-2" v-model="$i18n.locale" @change="updateLanguage($event.target.value)" variant="info">
		  <v-icon>mdi-chevron-down</v-icon>
		  <option hide-details v-for="(o, i) in locales_array" :key="i" :value="o.value" :selected="o.value === locale_default">{{ o.caption }}</option>
		</select>
	  </div>
	  <v-spacer></v-spacer>
	  <v-list>
		<v-list-item @click="listenLogout">
		  <v-list-item-title>Cerrar Sesión</v-list-item-title>
		</v-list-item>
	  </v-list>
	</v-app-bar>
  </template>
  