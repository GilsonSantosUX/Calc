<template>
<!-- https://www.origamid.com/projetos/css-grid-layout-guia-completo/ -->
    <div class="container">
        <div class="history">
            <i class="icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M13 3C8.03 3 4 7.03 4 12H1L4.89 15.89L4.96 16.03L9 12H6C6 8.13 9.13 5 13 5C16.87 5 20 8.13 20 12C20 15.87 16.87 19 13 19C11.07 19 9.32 18.21 8.06 16.94L6.64 18.36C8.27 19.99 10.51 21 13 21C17.97 21 22 16.97 22 12C22 7.03 17.97 3 13 3ZM12 8V13L16.28 15.54L17 14.33L13.5 12.25V8H12Z" fill="#E5E5E5"/>
                </svg>
            </i>
            <Display style="font-size:2rem;" number="3x3"/>
        </div>
        
        <Display number="9"/>
        <div class="keypad">
            <div class="keypad-number">
                <Button v-for="number in quant" :number="number" :key="number" @click="print(number)"/>
                <Button number="."/>
                <Button number="0"/>
                <Button>
                    <template v-slot:icon>
                    <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M44 6H14C12.62 6 11.54 6.7 10.82 7.76L0 24L10.82 40.22C11.54 41.28 12.62 42 14 42H44C46.2 42 48 40.2 48 38V10C48 7.8 46.2 6 44 6ZM38 31.18L35.18 34L28 26.82L20.82 34L18 31.18L25.18 24L18 16.82L20.82 14L28 21.18L35.18 14L38 16.82L30.82 24L38 31.18Z" fill="#E5E5E5"/>
                    </svg>
                    </template>
                </Button>
            </div>
            <div class="keypad-element">
                <Button number="x" @click="print('x')"/>
                <Button number="÷" @click="print('÷')"/>
                <Button number="+" @click="print('+')"/>
                <Button number="-" @click="print('-')"/>
            </div>
            <div class="keypad-actions">
                <Button style="height:112px;" @click="print('*')">
                <template v-slot:icon>
                    <svg width="64" height="64" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M53.3332 23.1733V10.6667H40.8265L31.9998 1.84L23.1732 10.6667H10.6665V23.1733L1.83984 32L10.6665 40.8267V53.3333H23.1732L31.9998 62.16L40.8265 53.3333H53.3332V40.8267L62.1598 32L53.3332 23.1733ZM31.9998 48C23.1732 48 15.9998 40.8267 15.9998 32C15.9998 23.1733 23.1732 16 31.9998 16C40.8265 16 47.9998 23.1733 47.9998 32C47.9998 40.8267 40.8265 48 31.9998 48ZM31.9998 21.3333C26.1065 21.3333 21.3332 26.1067 21.3332 32C21.3332 37.8933 26.1065 42.6667 31.9998 42.6667C37.8932 42.6667 42.6665 37.8933 42.6665 32C42.6665 26.1067 37.8932 21.3333 31.9998 21.3333Z" fill="#E5E5E5"/>
                    </svg>
                </template>
                </Button>
                <Button style="height:112px" @click="print('<-')">
                <template v-slot:icon>
                    <svg width="64" height="64" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M32 5.33331C17.2534 5.33331 5.33337 17.2533 5.33337 32C5.33337 46.7466 17.2534 58.6666 32 58.6666C46.7467 58.6666 58.6667 46.7466 58.6667 32C58.6667 17.2533 46.7467 5.33331 32 5.33331ZM45.3334 41.5733L41.5734 45.3333L32 35.76L22.4267 45.3333L18.6667 41.5733L28.24 32L18.6667 22.4266L22.4267 18.6666L32 28.24L41.5734 18.6666L45.3334 22.4266L35.76 32L45.3334 41.5733Z" fill="white"/>
                    </svg>
                </template>
                </Button>
                <Button number="=" @click="print('=')" style="height:112px;" class="active"/>
            </div>
            
        </div>
    </div>
</template>

<script>
import Display from './components/Display';
import Button from './components/Button';

export default {
  name: 'App',
  data:function () {
    return{
      quant: [7,8,9,4,5,6,1,2,3],
  }
  },
  components:{
      Display,
      Button
  },
  methods: {
      print(el){
          console.log(el);
      }
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Heebo:wght@100;300;400;500;600;700;800;900&display=swap');

:root{
    font-size:16px;
    font-family:'Roboto', sans-serif;

    --font-family:'Roboto', sans-serif;
    --font-secondary:'Heebo', sans-serif;

    --color-primary:#00AAff;

    --color-base-white:#FFFFFF;
    --theme-color-base:#232323;
    
}

*{
    font-family:var(--font-family);
    box-sizing:border-box;
    transition:all .25s ease-in-out;
}

html,body{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

a,link,li,ul,ol,p,strong,i,label,h1,h2,h3,h4,h5,h6{
    padding:0;
    margin:0;
}


#app{
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    gap:24px;

    color:var(--color-base-white);
    background: linear-gradient(116.82deg, #EAEAEA 0%, #D9D9D9 49.98%);
    // background:linear-gradient(90deg, rgba(0,30,34,1), rgba(0,60,50,1));
}

.container{
    min-height:620px;
    background: rgba(35,35,35,1);
    overflow:hidden;
    border-radius:16px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    flex-direction:column;
    box-shadow: 0px 16px 24px -16px rgba(0,0,0,.4);
}

.history{
    width:100%;
    display:flex;
    flex-direction:column;
    justify-content:flex-end;
    align-items:flex-end;
    justify-items:flex-end;
    align-content:flex-end;
    justify-items:flex-end;
    user-select: none;
    i.icon{
        padding:24px 24px 0 0;
        path{
            fill:var(--color-base-white);
        }
    }
    .display{
        padding:0 24px;
        font-weight:100;
    }
    
}

.keypad{
    width:100%;
    display:grid;
    grid-template-columns: 2fr 1fr 1fr;
    justify-content:space-between;
    padding-top:16px;
    align-content:center;
    align-items:center;
    justify-items:center;
    background:rgba(255,255,255,.08);
}

.keypad-number{
    display:grid;
    grid-template-columns: repeat(3, 1fr);
}

.keypad-element{
    display:grid;
    grid-template-columns: repeat(1, 1fr);
}

.keypad-actions{
    display:grid;
    grid-template-columns: repeat(1, 1fr);
}

// Served to screens that are at least 20em wide
@media screen and (min-width: 20em) {
    .container{
        width:100%;
        margin:0 16px;
    }
    .keypad{
        justify-content:space-around;
    }
    .keypad-number{
        width:100%;
        gap:0px 8px;
        &>button{
            min-width:64px;
        }
    }
    .keypad-element{
        width:100%;
        margin:0 8px;
        &>button{
            min-width:100%;
        }
    }
    .keypad-actions{
        width:100%;
        gap:24px 0px;
        &>button{
            min-width:100%;
        }
    }
}

// Served to screens that are at least 64em wide
@media screen and (min-width: 64em) {
    .keypad-number{
        gap:0px 60px;
    }
    .keypad-element{
        margin:0 60px;
    }
    .keypad-actions{
        gap:24px 0px;
    }
}

// Served to screens that are at least 90em wide
@media screen and (min-width: 90em) {
    .keypad-number{
        gap:0px 60px;
    }
    .keypad-element{
        margin:0 60px;
    }
    .keypad-actions{
        gap:24px 0px;
    }
}

// Served to screens that are at least 120em wide
@media screen and (min-width: 120em) {
    .container{
        width:840px;
    }

    .keypad-number{
        gap:0px 60px;
    }
    .keypad-element{
        margin:0 60px;
    }
    .keypad-actions{
        gap:24px 0px;
    }
}

</style>
