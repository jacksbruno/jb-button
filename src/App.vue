<template lang="pug">
  div
    .btn(:class="[format, size]")
      .gp-button(:class="[size, type, format, direcao, disabled ? 'disabled' : '', load]")
        .load(v-show="loader")
          div
        span(v-show="!prefix && !sufix") {{title || 'Button'}}
        ul(v-show="prefix || sufix")
          li(v-show="prefix", :class="[prefix && sufix ? 'expand' : '', prefix && !sufix ? 'remove-padding' : '']")
            slot(name="prefix")
          li(v-show="sufix", :class="prefix && sufix ? 'expand' : ''")
            slot(name="sufix")
</template>

<script>
export default {
  name: 'App',
  props: {
    title: {
      type: String
    },
    size: {
      type: String,
      default: 'medium'
    },
    type: {
      type: String,
      default: 'default'
    },
    format: {
      type: String,
      default: 'round'
    },
    prefix: {
      type: Boolean
    },
    sufix: {
      type: Boolean
    },
    expandLeft: {
      type: Boolean,
      default: true
    },
    disabled: {
      type: Boolean,
      default: false
    },
    loader: {
      type: Boolean,
      default: false
    }
  },
  watch: {
    expandLeft () {
      this.verificaDirecao()
    },
    loader () {
      this.verificaLoader()
    }
  },
  mounted () {
    this.verificaDirecao()
    this.verificaLoader()
  },
  data: () => ({
    direcao: 'left',
    load: ''
  }),
  methods: {
    verificaDirecao () {
      if (this.expandLeft) this.direcao = 'left'
      else this.direcao = 'right'
    },
    verificaLoader () {
      if (this.loader) this.load = 'loader'
      else this.load = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '@/variaveis.scss';
@import '@/placeholder.scss';
div{
  display: flex;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  .btn{
    position: relative;

    &.circle{
      &.mini{
        width: 28px;
        height: 28px;
      }
      &.small{
        width: 36px;
        height: 36px;
      }
      &.medium{
        width: 50px;
        height: 50px;
      }
      &.large{
        width: 60px;
        height: 60px;
      }
    }
    .gp-button{
      cursor: pointer;
      display: flex;
      align-items: center;
      color: $branco;
      font-weight: bold;
      user-select: none;

      &::before{
        content: "";
        position: absolute;
        width: 100%;
        height: 100%;
        z-index: -1;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        transition: .2s all ease-in-out;
      }
      &:hover{
        &::before{
          box-shadow: 0 1px 2px 0 rgba(0,0,0,.3), 0 4px 8px 0 rgba(0,0,0,.15);
          width: 106%;
          height: 106%;
        }
      }

      ul{
        padding: 0;
        display: flex;
        align-items: center;
        li{
          list-style: none;
          line-height: 0;
          transition: .2s all ease-in-out;

          label{
            color: $azulPadrao;
          }

          &:first-child{
            padding: 0 10px 0 0;
          }
          &.remove-padding{
            padding: 0 !important;
          }
        }
      }

      /********* Qaundo o Botão for Disabled *********/
      &.disabled{
        cursor: no-drop;
        opacity: .6;

        &:hover{
          &::before{
            width: 100%;
            height: 100%;
            box-shadow: none;
          }

          ul{
            li{
              label{
                animation: none !important;
                width: 100% !important;
              }
            }
          }
        }
      }

      /* Quando o Botão tiver Loader */

      &.loader{
        .load{
          position: absolute;
          top: 50%;
          left: 50%;
          transform: translate(-50%, -50%);
          div{
            background-image: url('./assets/load_branco.svg');
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
            width: 17px;
            height: 17px;
            animation: rotating .8s linear infinite;
          }
        }
        &.default{
          color: $branco;
          .load{
            div{
              background-image: url('./assets/load_azul.svg');
            }
          }
        }
        &.primary{
          color: $azulPadrao;
        }
        &.success{
          color: $verde;
        }
        &.danger{
          color: $vermelho;
        }
        @keyframes rotating {
          0%{
            transform: rotate(0deg);
          }
          100%{
            transform: rotate(360deg);
          }
        }
      }

      /*************** CSS Referente ao Tamanho do Botão ***************/
      &.mini{
        height: 28px;
        padding: 0 20px;
        font-size: 14px;
      }
      &.small{
        height: 36px;
        padding: 0 20px;
        font-size: 14px;
      }
      &.medium{
        height: 50px;
        padding: 0 30px;
        font-size: 16px;
      }
      &.large{
        height: 60px;
        padding: 0 30px;
        font-size: 18px;
      }

      /*************** CSS Refente ao Tipo do Botão ***************/
      /*----- Default -----*/
      &.default{
        position: relative;
        color: $azulPadrao;
        &::before{
          border: 1px solid $azulPadrao;
        }
      }

      /*----- Primary -----*/
      &.primary{
        &.circle{
          &::before{
            background: $azulPadrao;
          }
          &:hover{
            &::before{
              background: $azulPadrao;
              height: 106%;
              width: 106%;
            }
            ul{
              li{
                label{
                  color: $branco;
                }
              }
            }
          }
        }
        ul{
          li{
            label{
              color: $branco;
            }
            &:first-child{
              padding-right: 10px;
            }
          }
        }
        &::before{
          background: $azulPadrao;
        }
      }

      /*----- Success ------*/
      &.success{
        color: $branco;
        &.circle{
          &::before{
            border: none !important;
            background: $verde;
          }
          &:hover{
            &::before{
              background: $verde;
              height: 106%;
              width: 106%;
            }
            ul{
              li{
                label{
                  color: $branco;
                }
              }
            }
          }
        }
        &::before{
          background: $verde;
        }
        ul{
          li{
            label{
              color: $branco;
            }
          }
        }
      }

      /*----- Danger ------*/
      &.danger{
        position: relative;
        color: $branco;
        &.circle{
          &::before{
            border: none !important;
            background: $vermelho;
          }
          &:hover{
            &::before{
              background: $vermelho;
              height: 100%;
              width: 100%;
            }
            ul{
              li{
                padding: 0 !important;
                label{
                  color: $branco;
                }
              }
            }
          }
        }
        &::before{
          background: $vermelho;
        }
        ul{
          li{
            label{
              color: $branco;
            }
          }
        }
      }

      /*************** CSS Referente ao Formato do Botão ***************/
      /*----- Plain ------*/
      &.plain{
        &::before{
          border-radius: 5px;
        }
      }
      /*----- Round ------*/
      &.round{
        &::before{
          border-radius: 100px;
        }
      }
      /*----- Circle ------*/
      &.circle{
        position: absolute;
        right: 0;
        top: 0;
        z-index: 1;
        white-space: nowrap;
        border: none;

        &::before{
          background: #fff;
          border: 1px solid $azulPadrao;
          border-radius: 100px;
        }

        &.right{
          left: 0;
          right: auto;
        }

        ul{
          li{
            label{
              font-size: 0;
              color: $azulPadrao;
            }
            &:first-child{
              padding: 0;
            }
          }
        }

        &:hover{
          z-index: 5;
          &::before{
            width: 100%;
            height: 100%;
            background: $azulClaroHover;
          }
          ul{
            li{
              label{
                animation: .2s ease-in-out forwards cresce_botao;
              }
              @keyframes cresce_botao {
                0% {
                  opacity: 0;
                  font-size: 0;
                }
                50% {
                  opacity: 0;
                }
                100% {
                  opacity: 1;
                  font-size: 16px;
                }
              }
            }
          }
        }
        /* Circle Mini */
        &.mini{
          padding: 0 8px;
          user-select: none;
          img, i{
            @extend %tamanhoMinilImg;
          }
          &:hover{
            height: 38px;
            top: 50%;
            transform: translateY(-50%);
            ul{
              li.expand:first-child{
                padding: 0 5px 0 12px;
              }
              li.expand:last-child{
                padding: 0 12px 0 5px;
              }
            }
          }
        }
        /* Circle Small */
        &.small{
          padding: 0 10px;
          user-select: none;
          img, i{
            @extend %tamanhoNormalImg;
          }
          &:hover{
            ul{
              li.expand:first-child{
                padding: 0 5px 0 12px;
              }
              li.expand:last-child{
                padding: 0 12px 0 5px;
              }
            }
          }
        }
        /* Circle Medium */
        &.medium{
          padding: 0 17px;
          user-select: none;
          img, i{
            @extend %tamanhoNormalImg;
          }
          &::before{
            border: 2px solid $azulPadrao;
          }
          &:hover{
            ul{
              li.expand:first-child{
                padding: 0 5px 0 12px;
              }
              li.expand:last-child{
                padding: 0 12px 0 5px;
              }
            }
          }
        }
        /* Circle Large */
        &.large{
          padding: 0 18px;
          user-select: none;
          img, i{
            @extend %tamanhoLargeImg;
          }
          &::before{
            border: 2px solid $azulPadrao;
          }
          &:hover{
            ul{
              li.expand:first-child{
                padding: 0 5px 0 12px;
              }
              li.expand:last-child{
                padding: 0 12px 0 5px;
              }
            }
          }
        }
      }
    }
  }
}
</style>
