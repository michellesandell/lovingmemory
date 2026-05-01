<template>
  <div>
    <Nuxt />
  </div>
</template>

<style lang="scss">
// ── Catppuccin Mocha palette ─────────────────
$base:      #1e1e2e;
$mantle:    #181825;
$surface0:  #313244;
$text:      #cdd6f4;
$subtext0:  #a6adc8;
$pink:      #f5c2e7;
$mauve:     #cba6f7;

$highlight:       $pink;
$highlightmuted:  rgba($pink, 0.85);
$background:      $base;

html {
  font-family: 'Lato', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.fa-ulist {
    margin: 10px 0px!important;
    list-style-type: none;
    position: relative;
}
.fa-icon::before {
    display: inline-block;
    text-rendering: auto;
    -webkit-font-smoothing: antialiased;
}

.fa-list::before {
    font: var(--fa-font-solid);
    content: "\f105";
    color: $highlight;
    margin-right: 10px;
    font-size: 12px;
    position: absolute;
    top: 0%;
    left: 5px;
    height: 100%;
    display: flex;
    align-items: center;
}

.fa-list {
    margin: 0!important;
    padding: 6px 0;
    padding-left: 23px;
    min-height: 28px;
    position: relative;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  @media screen and (max-width: 800px) {
    flex-direction: column;
    justify-content: flex-start;
  }
}
.icon {
  margin-right: 10px;
  font-size: 22px;
  height:28px;
  width: 27.5px;
}
.section {
  flex: 0 0 50%;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  @media screen and (max-width: 800px) {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    min-height: auto;
    height: 100%!important;
    padding-bottom: 90px!important;
  }
  &.links {
    background-image: url('~assets/corner.svg');
    background-position: bottom 20px left 20px;
    background-repeat: no-repeat;
    background-size: 200px;
    @media screen and (max-width: 800px) {
      padding: 0;
      background-position: bottom 2px left 2px;
      background-size: 150px;
      position: fixed;
      top: auto;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 80px!important;
      background: rgba($mantle, 0.85);
      padding-bottom: 0px!important;
      z-index: 2;
      backdrop-filter: blur(5px);
      ul {
        display: flex;
        justify-content: space-around;
        width: 100%;
        height: 100%;
        li {
          height: 100%;
          width: 20%;
          .icon {
            margin: 0;
          }
          a {
            height: 100%;
            padding: 0;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: $subtext0;
            font-size: 12px;
            &.nuxt-link-exact-active {
              color: $text;
              .icon {
                color: lighten($highlight, 5%);
              }
            }
            .menu span {
              display: none;
            }
          }
        }
      }
    }
    ul {
      padding: 0;
    }
  }

  &.tribute {
    background: $background;
    justify-content: space-evenly;
    overflow: auto;
    height: 100vh;
    @media (max-height: 600px) {
      justify-content: normal;
    }
    img {
      box-sizing: content-box;
      border: 8px solid $surface0;
      box-shadow: 0 0 10px 3px rgba(0, 0, 0, 0.6);
    }
  }
  &.details {
    background: $background;
    color: $text;
    align-items: flex-start;
    text-align: left;
    padding: 40px;
    justify-content: normal;
    overflow: auto;
    height: 100vh;

    p {
      margin: 10px 0;
      font-weight: 300;
      &.highlight {
        background: $highlightmuted;
        padding: 20px;
        font-weight: 400;
        color: $base;
      }
    }
    .fa-li {
      color: $highlight;
    }
    ul {
      font-weight: 300;
      margin: 0 0 0 25px;
      padding: 0;
      li {
        margin: 10px 0;
      }
    }
    .title {
      margin: 0px 0 25px;
    }
    h2 {
      margin: 40px 0 5px;
      align-items: center;
      display: flex;
      span, em {
        background: $highlightmuted;
        padding: 3px 7px;
        font-size: 16px;
        margin-left: 15px;
        border-radius: 4px;
        color: $base;
      }
    }
  }
  .button {
    padding: 15px 30px;
    border-radius: 4px;
    font-size: 18px;
    background: $highlight;
    text-decoration: none;
    color: $base;
    margin: 10px 0;
    box-shadow: 0 0 5px 2px rgba($mantle, 0.6);
    border-top: 1px solid rgba($text, 0.2);
    display: inline-block;
  }
}
ul {
  list-style: none;
  font-weight: 700;
  text-align: left;
  font-size: 16px;
  li {
  }
  a {
    color: $highlight;
    text-decoration: none;
    padding: 10px 0;
    display: flex;
    align-items: center;
    &.nuxt-link-exact-active {
      color: $text;
    }
  }
}
.highlight {
  background: $highlight;
  padding: 3px 7px;
  font-size: 16px;
  margin-left: 15px;
  border-radius: 4px;
  display: inline-block;
  color: $base;
}

.menu {
  small {
    color: $subtext0;
  }
}
.name {
  font-size: 40px;
  color: $text;
  font-weight: 300;
}
.title {
  font-family: 'Pinyon Script', cursive;
  display: block;
  font-weight: 300;
  font-size: 50px;
  color: $text;
  letter-spacing: 1px;
  margin: 40px 0;
  @media screen and (max-width: 800px) {
    font-size: 40px;
    margin: 30px 0;
  }
}

.subtitle {
  font-weight: 300;
  font-size: 14px;
  color: $subtext0;
  margin: 40px 0;
  @media screen and (max-width: 800px) {
    margin: 25px 0;
  }
}

// ... rest of SVG/FontAwesome rules unchanged ...
.svg-inline--fa {
    display: inline-block;
    font-size: inherit;
    height: 1em;
    overflow: visible;
    vertical-align: -.125em;
}
.fa-fw {
    text-align: center;
}
.fa-ul {
    list-style-type: none;
    position: relative;
}
.fa-li {
    left: -2em;
    position: absolute;
    text-align: center;
    width: 2em;
    line-height: inherit;
}
.svg-inline--fa.fa-w-8 {
    width: .5em;
}
.svg-inline--fa.fa-fw {
    width: 1.25em;
}
</style>