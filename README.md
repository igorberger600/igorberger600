## Hi there 👋

<!--
**igorberger600/igorberger600** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
let cor;
let circuloX; // horizontal
let circuloY; // vertical

function setup() {
  createCanvas(400, 400);
  background(color(100, 0 , 0));
  cor = color(random(0, 255), random(0, 255), random(0, 255));
  
  circuloX = [0, 0, 0];
  circuloY = [random(height), random(height), random(height)];
}

function draw() {
  
  fill(cor);
  
  for(let contador in circuloX) {
    circle(circuloX[contador], circuloY[contador], 50);    
    circuloX[contador]+= random(0,3);
    circuloY[contador]+= random(-3,3); 
    
    if(circuloX[contador] >= width){
      circuloX[contador] = 0;
      circuloY[contador] = random(height);
    }
  }
  
  if(mouseIsPressed){
    cor = color(random(0, 255), random(0, 255), random(0, 255), random(0, 100));
  }
}
