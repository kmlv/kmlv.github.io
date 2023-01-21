---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% include tags_names.html %}



{% assign button_style = 'margin: 10px;font-size: 14px;font-weight: bold;width: 100px;height: 30px;padding:1px;background:#505050;color:#efeded;outline:none;
    border-radius: 5px;border: 2px solid black;transition: 0.3s;' %}
<div>
    {% for tag_sample in tags_names %}
  	<button id = "b_{{tag_sample}}" onclick="checked('{{tag_sample}}')" style="{{button_style}}" onmouseover="func_hover('b_{{tag_sample}}')" onmouseout= "func_out('{{tag_sample}}')">
	    <input type="checkbox" id="{{tag_sample}}" disabled="disabled" checked=checked style="display:none">{{tag_sample}}</button>
    {%endfor%}
    
</div>
  <div><h2> Publications </h2></div>
{% for post in site.research reversed %}
  {% if post.working == 0 %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}


<div><h2> Working Papers </h2> </div>
{% for post in site.research reversed %}
  {% if post.working == 1 %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}
 
 
 <div><h2> Work in Progress </h2></div>
{% for post in site.research reversed %}
  {% if post.working == 2 %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}


<script> 
  
  function checked(tag){
         
          let chec = document.getElementById(tag);
	  let b_tag = 'b_'+tag;
	  let button_tag = document.getElementById(b_tag);
	  
          
  
          if (chec.checked == false){
              chec.checked = true; 
              toggle(tag,'block');
	      button_tag.style.border = "2px solid black";
	      button_tag.style.backgroundColor = "#505050";
              
          }
          else if (chec.checked == true) {
              chec.checked = false;
              toggle(tag,'none');
	      button_tag.style.border = "0px solid black";
	      button_tag.style.backgroundColor = "#878484";
              
          }
  }
  
  function toggle(className, displayState){
          
          var elements = document.getElementsByClassName(className);
          for (var i = 0; i < elements.length; i++){
               elements[i].style.display = displayState;
          }
  }
     
  function func_hover(tag){
    let elemento = document.getElementById(tag);
    elemento.style.backgroundColor = "#878484";
    elemento.style.border = "#2px solid black";
					      
    
    
  }
    
  function func_out(tag){
    
    let b_tag = 'b_'+tag;
    let chec = document.getElementById(tag);
    let elemento = document.getElementById(b_tag);
    if (chec.checked == false){elemento.style.border = "#0px solid black";}	
    else {elemento.style.backgroundColor = "#505050";}
   
    
	}
 
            
</script>
