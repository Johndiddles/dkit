<template>
    <Page>
        <!--<ActionBar title="Diddles Kitchen" class="ActionBar" width="100%" horizontalAlignment="center"/> -->
        <ActionBar width="100%" background="#1a1e1a">
            <StackLayout class="stack1" width="">
                <Label text="Diddles Kitchen 😜" class="ActionBar" />
                <Label text="The Best of African Dishes" class="motto" />
            </StackLayout>
        </ActionBar>
        <ScrollView class="body1">
            <StackLayout class="" verticalAlignment="center">
                <Label text="USERNAME" class="placeHolder" />
                <TextField hint="Email/Username..." class="login"/>
                <!-- <Label text="Password" class="placeHolder" /> -->
                <TextField hint="Password..." class="login"/>
                <Button text="Sign In" class="loginbtn" @tap="signin"/>
            </StackLayout>
        </ScrollView>
    </Page>
</template>

<script >
    import catalogue from './catalogue.vue';
    export default {
        data() {
          return {

          }
        },
        methods: {
            signin() {
                this.$navigateTo(catalogue);
            },
        },
           
      }
</script>

<style scoped>
    .stack1 {
        background-color: #1a1e1a;
        color: #ffffff;
    }
    .ActionBar {
        background-color: #1a1e1a;
        color: #ffffff;
        font-size: 25;
        font-weight: 500;
        text-align: center;
        width: ;
        margin: 0;
    }

    .motto {
        font-size: 12;
        font-weight: 300;
        font-style: italic;
        margin: 0;
        text-align: center;

    }

    .body1 {
        background-image: url("https://www.preciouscore.com/wp-content/uploads/2019/02/Mandazi-recipe.jpg");
        background-position: center;
        background-repeat: no-repeat;
        height: 100%;
        margin: 0;
        opacity: 1;
        filter: blur(20px);
        -webkit-filter: blur(20px);
    }

    .placeHolder {
        background: ;
        height: 20;
        margin-bottom: -10;
        margin-right: 5;
        color: #000000;
        font-size: 15;
        font-weight: 900;
        text-align: right;
        opacity: 0.8;

    }
    .login {
        margin: 30px;
        background-color: ;
        opacity: ;
        color: #5a5e5a;
        margin: 0;
        text-align: right;
    }

    .loginbtn {
        background-color: #1a1e1a;
        color: #ffffff;
        font-size: 18;
        font-weight: 500;
        opacity: 0.9;
    }

</style>
