    <template>
      <div class="carouseltop">
        <slot :currentSlide="currentSlide"/>

      <!-- Navegação -->

      <div class="navigate">  
          <div class="botao-page esquerda">
            <i class="fas fa-chevron-left"></i>
          </div>
          <div class="botao-page direita">
            <i class="fas fa-chevron-right"></i>
        </div>


      </div>


      </div>
    </template>
    
    <script>

    import {ref, onMounted } from "vue";

    export default {
        setup() {
          const currentSlide = ref(2);
          const getSlideCount = ref(null);

          //próximo slide
          const nextSlide = () => {
            if (currentSlide.value === getSlideCount.value) {
              currentSlide.value = 1;
              return;
            }
            
            currentSlide.value +=1;
          }

          //slide anterior


          onMounted ( () => {
            getSlideCount.value = document.querySelectorAll('.slidertop').length;
            console.log(getSlideCount.value)

          }
           )


          

          return {currentSlide};
        }
    }
    </script>
    
    <style lang="scss">

    .navigate {

        padding: 0 16px;
        height: 100%;
        width: 100%;
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
    }

      .botao-page {

      display: flex;
      flex: 1;
      

    }


    .direita {

        justify-content: flex-end;
    }


    i {

      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 80%;
      width: 40px;
      
      height: 40px;
      
      color: rgb(155, 20, 20)
      

    }

   .fas {

      height: 50px;
   }

   
    </style>