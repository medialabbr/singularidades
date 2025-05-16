---
layout: abertura
---

<script>
var target_date = new Date("sep 11, 2023").getTime(); 
var dias, horas, minutos, segundos;
var regressiva = document.getElementById("regressiva");

setInterval(function () {

    var current_date = new Date().getTime();
    var segundos_f = (target_date - current_date) / 1000;

dias = parseInt(segundos_f / 86400);
    segundos_f = segundos_f % 86400;
    
    horas = parseInt(segundos_f / 3600);
    segundos_f = segundos_f % 3600;
    
    minutos = parseInt(segundos_f / 60);
    segundos = parseInt(segundos_f % 60);

    document.getElementById('dia').innerHTML = dias;
document.getElementById('hora').innerHTML = horas;
document.getElementById('minuto').innerHTML = minutos;
document.getElementById('segundo').innerHTML = segundos;
  

}, 1000);
</script>
<style>
  .contagem{
width:300px;
height:70px;
margin: 8em auto 0;
}

.numero
{
min-width: 20px;
max-width: 55px;
background-color: #efefef;
color: #000000;
font-size: 22px;
margin: 5px;
text-align: center;
border-radius: 5px;
padding: 5px;
}---
title: Home
layout: default
pagination: 
  enabled: true
---
<div class="container-fluid">
  <div class="row">
  {% for post in paginator.posts %}
    <div class="card  col-lg-4 col-xl-3 border-0">
      {% if post.thumbnail %}
        <div class="box">
          <img src="{{ site.baseurl }}/{{ post.thumbnail }}" /> 
        </div>
      {% else %}
        <img src="" />
      {% endif %}
     
      <p>
        <a style="text-decoration: none;" href="{{ BASE_PATH }}{{ post.url | remove: '/index.html' }}" class="shuf">
          {{ post.title }}
        </a>
      </p>
    </div>
  {% endfor %}
  </div>
  <div class="row">
    <div class="pagina col-sm-11">
      {% if paginator.page_trail %}
        {% for trail in paginator.page_trail %}
          <li {% if page.url == trail.path %}{% endif %}>
            <a href="{{ trail.path | prepend: site.baseurl }}" title="{{trail.title}}">{{ trail.num }}</a>.
          </li>
        {% endfor %}
      {% endif %}
    </div>
  </div>
</div>


.legenda{
height: 25px;
line-height: 10px;
font-size:12px;

text-align: center;
}

</style>

<div class="container-fluid">
  <div class="row">
    <div class="ficha-tecnica col-sm-10">
    <div class="text-center">
    <img src="/assets/abertura.gif" class="img-fluid" alt="ABERTURA / OPENING "/> 
    </div>
  


  <div class="contagem">
  <table><tr><td><div class="numero" id="dia"></div></td><td><div class="numero" id="hora"></div></td><td><div class="numero" id="minuto"></div></td><td><div class="numero" id="segundo"></div></td></tr>
  <tr style="height:20px"><td><p class="legenda">dias</p></td><td><p class="legenda">horas</p></td><td><p class="legenda">min</p></td><td><p class="legenda">seg</p></td></tr></table>
  </div>

  </div>
  </div>
</div>
