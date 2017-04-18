<template>
  <div id="app">
    <h2> Search JavaScript</h2>
    <div class="search-wrapper">
      <input type="text" v-model="info" placeholder=""/>
      <label> Search !</label>
    </div>
    <div class="wrapper">
      <div class="card" v-for="post in searchPost">
        <a v-bind:href="post.link" target="_blank" v-bind:style="{textAlign: 'center'}">
          <img v-bind:src="post.img">
          <small>Posted by: {{post.author}}</small>
          {{post.title}}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
  class Post {
    constructor (title, link, author, img) {
      this.title = title
      this.link = link
      this.author = author
      this.img = img
    }
  }
  export default {
    name: 'app',
    data () {
      return {
        info: '',
        postList: [
          new Post(
            'Vue.js',
            'https://vuejs.org',
            '****',
            'https://vuejs.org//images/logo.png'
          ),
          new Post(
            'React.js',
            'https://facebook.github.io/react/',
            '****',
            'http://daynin.github.io/clojurescript-presentation/img/react-logo.png'
          ),
          new Post(
            'Ember.js',
            'http://emberjs.com/',
            '****',
            'http://www.gravatar.com/avatar/0cf15665a9146ba852bf042b0652780a?s=200'
          ),
          new Post(
            'Meteor.js',
            'https://www.meteor.com/',
            '****',
            'http://hacktivist.in/introduction-to-nodejs-mongodb-meteor/img/meteor.png'
          ),
          new Post(
            'Aurelia',
            'http://aurelia.io/',
            '****',
            'https://cdn.auth0.com/blog/aurelia-logo.png'
          ),
          new Post(
            'Node.js',
            'https://nodejs.org/en/',
            '****',
            'https://code-maven.com/img/node.png'
          ),
          new Post(
            'Pusher',
            'https://pusher.com/',
            '****',
            'https://avatars1.githubusercontent.com/u/739550?v=3&s=400'
          ),
          new Post(
            'Feathers.js',
            'http://feathersjs.com/',
            '****',
            'https://cdn.worldvectorlogo.com/logos/feathersjs.svg'
          ),
          new Post(
            'Angular.js',
            'https://angular.io/',
            '****',
            'https://angular.io/resources/images/logos/angular/angular.svg'
          ),
          new Post(
            'Dojo toolkit',
            'http://dojotoolkit.org/',
            '****',
            'https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/Dojo_toolkit_logo.svg/1200px-Dojo_toolkit_logo.svg.png'
          ),
          new Post(
            'jQuery',
            'https://jquery.com/',
            '****',
            'http://precision-software.com/wp-content/uploads/2014/04/jQurery.gif'
          ),
          new Post(
            'Mootools',
            'https://mootools.net/',
            '****',
            'https://mootools.net/images/logo/mootools.png'
          ),
          new Post(
            'PrototypeJs',
            'http://prototypejs.org/',
            '****',
            'http://prototypejs.org/images/header-logo.png'
          ),
          new Post(
            'YUI js',
            'https://yuilibrary.com/',
            '****',
            'https://yuilibrary.com/img/yui-logo.png'
          ),
          new Post(
            'Any Chart',
            'http://www.anychart.com/',
            '****',
            'http://www.anychart.com/_design/img/static/AnyChart-circle.png'
          ),
          new Post(
            'D3js',
            'https://d3js.org/',
            '****',
            'https://avatars1.githubusercontent.com/u/1562726?v=3&s=400'
          ),
          new Post(
            'p5*js',
            'https://p5js.org/',
            '****',
            'https://p5js.org/assets/img/p5js.svg'
          ),
          new Post(
            'Velocity.js',
            'http://velocityjs.org/',
            '****',
            'https://pbs.twimg.com/media/Ct1iQJvW8AAq-Mz.jpg'
          ),
          new Post(
            'Whitestorm JS',
            'https://whsjs.io/#/',
            '****',
            'https://avatars3.githubusercontent.com/u/16437392?v=3&s=200'
          ),
          new Post(
            'PixiJS',
            'http://www.pixijs.com/',
            '****',
            'http://www.pixijs.com/img/pixijs-v4-logo.png'
          ),
          new Post(
            'w2ui',
            'http://w2ui.com/web/',
            '****',
            'http://w2ui.com/web/img/w2ui.png'
          ),
          new Post(
            'Three.js',
            'https://threejs.org/',
            '****',
            'https://www.digitaltactics.co.uk/wp-content/uploads/sites/2/2015/11/three-js-logo-480x368.png'
          ),
          new Post(
            'Backbone.js',
            'http://backbonejs.org/',
            '****',
            'http://backbonejs.org/docs/images/backbone.png'
          ),
          new Post(
            'Knockout',
            'http://knockoutjs.com/',
            '****',
            'http://knockoutjs.com/img/ko-logo.png'
          )
        ]
      }
    },
    computed: {
      searchPost () {
        return this.postList.filter(post => {
          return post.title.toLowerCase().includes(this.info) || post.title.includes(this.info)
        })
      }
    }
  }
</script>

<style>
  #app {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    margin-top: 30px;
  }

  #app h2 {
    font-weight: 400;
    text-transform: uppercase;
  }

  #app .search-wrapper {
    position: relative;
  }

  #app .search-wrapper label {
    position: absolute;
    font-size: 12px;
    color: rgba(0, 0, 0, 0.5);
    top: 8px;
    left: 12px;
    z-index: 1;
    transition: .15s all ease-in-out;
  }

  #app .search-wrapper input {
    padding: 4px 12px;
    color: rgba(0, 0, 0, 0.7);
    border: 1px solid rgba(0, 0, 0, 0.12);
    transition: .15s all ease-in-out;
    background: white;
    margin-bottom: 10px;
  }

  #app .search-wrapper input:focus {
    outline: none;
    transform: scale(1.05);
    border:none;
    border-bottom: 1px solid #333;

  }

  #app .search-wrapper input:focus + label {
    font-size: 10px;
    transform: translateY(-24px) translateX(-12px);
  }

  #app .search-wrapper input::-webkit-input-placeholder {
    font-size: 12px;
    color: rgba(0, 0, 0, 0.5);
    font-weight: 100;
  }

  #app .wrapper {
    display: flex;
    justify-content: center;
    max-width: 1332px;
    flex-wrap: wrap;
    padding-top: 12px;
  }

  #app .card {
    box-shadow: rgba(0, 0, 0, 0.11765) 0px 1px 6px, rgba(0, 0, 0, 0.11765) 0px 1px 4px;
    max-width: 126px;
    margin: 14px;
    transition: .15s all ease-in-out;
  }

  #app .card:hover {
    transform: scale(1.1);
  }

  #app .card a {
    text-decoration: none;
    padding: 14px;
    color: #03A9F4;
    font-size: 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  #app .card a img {
    height: 100px;
    width: 100px;
  }

  #app .card a small {
    font-size: 10px;
    padding: 4px;
  }

  #app .box {
    width: 100px;
    height: 100px;
    border: 1px solid rgba(0, 0, 0, 0.12);
  }

</style>
