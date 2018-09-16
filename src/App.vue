<template>
  <div id="app" class="page">


    <div class="search">
      <div class="">
        <label>search</label>
        <input type="text" placeholder="search" v-model="search" @keyup.enter="filteredList">
        <button @click="filteredList">search</button>
      </div>
      <div>
        <label>Add new Student</label>
        <input type="text" placeholder="add person" v-model="newItem" @keyup.enter="addItem">
        <button @click="addItem">Add Item</button>
      </div>
    </div>

    <ul class="student-list">
      <li class="student-item cf" v-for="(student, i) in filteredList">
        <div class="student-details">
          <img class="avatar" :src="student.src">
          <h3>{{student.name}}</h3>
          <span class="email">{{student.email}}</span>
        </div>
        <div class="joined-details">
          <span class="date">{{student.date}}</span>
        </div>
      </li>
    </ul>

  </div>
</template>

<script>
import Students from './components/Students.vue';
import Heading from './components/Heading.vue';
import Search from './components/Search.vue';


export default {
  name: 'app',
  components: {
      Students,
    Search,
      Heading
  },
   methods: {
       addItem: function(){
           this.students.push({name:this.newItem, email: this.newItem+'@example.com', src:'https://randomuser.me/api/portraits/thumb/women/67.jpg', date: 'joined just now' });
           this.newItem='';
       },
   },
    computed: {
        filteredList() {
            return this.students.filter(student => {
                return student.name.toLowerCase().includes(this.search.toLowerCase())
            })
        }
    },


    data(){
        return({
            postFontSize: 1,
            show: true,
            search: '',
            newItem: '',
            searchLabel:'Search',
            title: 'Students',
            students: [
                {
                    name: 'iboya vat',
                    email: 'iboya.vat@example.com',
                    date: 'Joined 07/15/15',
                    src: 'https://randomuser.me/api/portraits/thumb/women/67.jpg'
                },
                {
                    name: 'toni vat2',
                    email: 'iboya.vat@example.com2',
                    date: 'Joined 07/15/152',
                    src: 'https://randomuser.me/api/portraits/thumb/women/67.jpg'
                },
                {
                    name: 'john vat2',
                    email: 'iboya.vat@example.com2',
                    date: 'Joined 07/15/152',
                    src: 'https://randomuser.me/api/portraits/thumb/women/67.jpg'
                },
                {
                    name: 'peter vat2',
                    email: 'iboya.vat@example.com2',
                    date: 'Joined 07/15/152',
                    src: 'https://randomuser.me/api/portraits/thumb/women/67.jpg'
                },
                {
                    name: 'sara vat2',
                    email: 'iboya.vat@example.com2',
                    date: 'Joined 07/15/152',
                    src: 'https://randomuser.me/api/portraits/thumb/women/67.jpg'
                }
            ]
        })
    }
};
</script>

<style>
  /* http://meyerweb.com/eric/tools/css/reset/
   v2.0 | 20110126
   License: none (public domain)
*/

  html, body, div, span, applet, object, iframe,
  h1, h2, h3, h4, h5, h6, p, blockquote, pre,
  a, abbr, acronym, address, big, cite, code,
  del, dfn, em, img, ins, kbd, q, s, samp,
  small, strike, strong, sub, sup, tt, var,
  b, u, i, center,
  dl, dt, dd, ol, ul, li,
  fieldset, form, label, legend,
  table, caption, tbody, tfoot, thead, tr, th, td,
  article, aside, canvas, details, embed,
  figure, figcaption, footer, header, hgroup,
  menu, nav, output, ruby, section, summary,
  time, mark, audio, video {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font: inherit;
    vertical-align: baseline;
  }
  /* HTML5 display-role reset for older browsers */
  article, aside, details, figcaption, figure,
  footer, header, hgroup, menu, nav, section {
    display: block;
  }
  body {
    line-height: 1;
  }
  ol, ul {
    list-style: none;
  }
  blockquote, q {
    quotes: none;
  }
  blockquote:before, blockquote:after,
  q:before, q:after {
    content: '';
    content: none;
  }
  table {
    border-collapse: collapse;
    border-spacing: 0;
  }

  .cf:after {
    content: ".";
    visibility: hidden;
    display: block;
    height: 0;
    clear: both;
  }
  body{
    background-color: #e1f1f6;
    font-family: Helvetica, sans-serif;
    color: #222;
  }

  .search{
    display:flex;
    justify-content:space-between;
  }
  label{
    margin-right:10px;
  }
  input{
    margin-right:10px;
  }

  .page{
    margin: 50px auto;
    width: 70%;
    background-color: #fff;
    border-radius: 5px;
    padding: 50px;
  }

  .page-header{
    margin-bottom: 20px;
  }
  .page-header h2{
    float: left;
    font-size: 22px;
    text-transform: uppercase;
    font-weight: bold;
    color: #555;
  }

  .page-header .student-search{
    float: right;
  }

  .page-header .student-search input{
    border-radius: 5px;
    border: 1px solid #eaeaea;
    padding: 8px 15px;
    font-size: 14px;
  }

  .page-header .student-search button{
    border-radius: 5px;
    border: 1px solid #eaeaea;
    padding: 8px 15px;
    font-size: 14px;
    background-color: #4ba6c3;
    color: #fff
  }

  .student-list{}

  .student-item{
    margin: 0 0 20px 0;
    padding: 0 0 20px 0;
    border-bottom: 1px solid #eaeaea;
    display: flex;
    width: 100%;
  }

  .student-details{
    width: 50%;
    float: left;
  }

  .student-details .avatar{
    width: 40px;
    height: auto;
    border-radius: 20px;
    float: left;
    margin-right: 14px
  }

  .student-details h3{
    margin: 4px 0 2px 0;
    font-weight: bold;
    color: #4ba6c3;
  }

  .student-details .email{
    color: #888;
    font-size: 14px;
  }


  .joined-details{
    width: 50%;
    float: left;
    text-align: right;
  }

  .joined-details .date{
    margin-top: 15px;
    display: block;
    font-size: 14px;
    color: #999;
  }

  .student-item:last-child{
    margin: 0;
    padding: 0;
    border-bottom: none;
  }

  .pagination{
    margin: 40px 0 0 0;
    text-align: center;
  }

  .pagination li{
    display: inline;
  }

  .pagination li a{
    border: 1px solid #eaeaea;
    border-radius: 5px;
    padding: 3px 8px;
    text-decoration: none;
    color: #4ba6c3;
  }

  .pagination li a.active,
  .pagination li a:hover{
    background-color: #4ba6c3;
    color: #fff;
  }
</style>
