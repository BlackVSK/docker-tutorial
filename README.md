**Docker**

Tutorial introdutório sobre [docker](https://www.docker.com/) para desenvolvimento de aplicações, focando na criação de ambientes isolados e reprodutíveis. Este tutorial vai desde a construação de um Dockerfile até o deploy de containers na AWS, passando por conceitos como containers, dockerHub, volumes, networks e docker-compose. Esse tutorial foi construído a partir do curso em vídeo [Docker & Kubernetes: The Practical Guide 2025 Edition](https://www.udemy.com/course/docker-kubernetes-the-practical-guide/?couponCode=ST7MT290425G3#instructor-2) do [Maximilian Schwarzmüller](https://github.com/maxschwarzmueller).
Esse tutorial está em constante desenvolvimento, envie sugestões e correções para meu [email](mailto:phrod2007@gmail.com).

---

**Trilha do Curso**

Esse tutorial é parte de uma trilha de aprendizado. Siga os links abaixo para acessar os outros cursos da trilha:

- [**Programação I**](https://github.com/ldmfabio/Programacao) ([Prof. Fábio Longo de Moura](https://github.com/ldmfabio)): Lógica de Programação com JavaScript.
- [**Desenvolvimento Web II**](https://eduardo-da-silva.github.io/aula-desenvolvimento-web/) ([Prof. Eduardo da Silva](https://github.com/eduardo-da-silva)): Desenvolvimento front-end com VueJS.
- [**Desenvolvimento Dispositivos Móveis III**](https://eduardo-da-silva.github.io/aula-desenvolvimento-mobile/) ([Prof. Eduardo da Silva](https://github.com/eduardo-da-silva)): Desenvolvimento para dispositivos móveis com Vue + Vite + PWA.
- [**Desenvolvimento Web III - Atual**](https://github.com/marrcandre/django-drf-tutorial) ([Prof. Marco André Lopes Mendes](https://github.com/marrcandre/)): Desenvolvimento back-end com Django e DRF, utilizando o [modelo de projeto](https://github.com/marrcandre/template_django_pdm).
- [**Desenvolvimento Web III (2023)**](https://github.com/marrcandre/django-drf-tutorial) ([Prof. Marco André Lopes Mendes](https://github.com/marrcandre/)): Desenvolvimento back-end com Django e DRF, do zero, sem utilizar o template.

Bons estudos!
---

# 1. O que é docker?

**Docker** é uma tecnologia de containers usada para criar e gerenciar containers. Em um software de desenvolvimento, o container é uma unidade padronizada de software, isso significa que é um pacote de código importante para que as dependências e ferramentas necessárias executem o código. Imagine que eu tenho uma peça de quebra cabeça e eu tiro uma peça desse quebra cabeça para colocar em outro, essa peça não foi feita para se encaixar a esse outro quebra cabeça e a única solução seria ter um quebra cabeça exatamente igual o meu. No contexto de desenvolvimento, o quebra cabeça seria meu ambiente de desenvolvimento e a peça desse quebra cabeça seria a aplicação, quando eu tiro a minha aplicação do meu ambiente que foi configurado conforme a necessidades da minha aplicação e passa para um ambiente na qual foi configurado para as necessidades de outra aplicação com diferentes necessidades, a minha aplicação pode e vai apresentar erros, é onde ocorre a famosa situação *" na minha máquina funciona "* e foi pensando na resolução desse tipo de problema que o docker foi criado. Vamos enteder muito mais colocando a mão na massa

![Quebra cabeça](imgs/quebra-cabeça.png "Quebra cabeça")

