# festival

Descreva aqui as alterações/correções que fez


completei o concerto = Concerto.objects.get(id=id) e o dias = Dia.objects.all() dentro do views.py


dentro do palcos.html tinha o href vazio por isso adicionei o <a href="{% url 'concerto' concerto.id %}"> tanto no dias.html e no palcos.html


criei o dias.html e fez este codigo 

{% extends 'festival/layout.html' %}

{% block content %}
    
{% for dia in dias %}
<h3>{{dia}}</h3>

    {% for concerto in dia.concertos.all %}
        <article class="card">
            <a href="{% url 'concerto' concerto.id %}">{{ concerto.banda.nome }} - {{ concerto.dia }}, {{ concerto.hora }}</a>
        </article>
    {% endfor %}

{% endfor %}

{% endblock %}



por fim alterei o concertos para concerto dentro do concerto.html
    

