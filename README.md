<style>
body {
  background: linear-gradient(45deg, #0a0a0a, #1a1a2e, #16213e, #0f3460, #e94560, #16213e);
  background-size: 400% 400%;
  animation: gradientShift 15s ease infinite;
  color: #c0c0c0;
  font-family: 'Fira Code', monospace;
  margin: 0;
  padding: 20px;
}

@keyframes gradientShift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.floating-code {
  position: absolute;
  font-size: 14px;
  color: rgba(0, 198, 255, 0.3);
  animation: float 20s linear infinite;
  pointer-events: none;
}

@keyframes float {
  0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
  10% { opacity: 1; }
  90% { opacity: 1; }
  100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
}

.section {
  background-color: rgba(30, 30, 47, 0.9);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(0, 198, 255, 0.3);
  box-shadow: 0 0 20px rgba(0, 198, 255, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.section:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 198, 255, 0.2);
}
</style>

<!-- Floating code elements for developer vibe -->
<div class="floating-code" style="left: 10%; animation-delay: 0s;">{ console.log('Hello World'); }</div>
<div class="floating-code" style="left: 20%; animation-delay: 5s;">function animate() { ... }</div>
<div class="floating-code" style="left: 30%; animation-delay: 10s;"><div> </div></div>
<div class="floating-code" style="left: 40%; animation-delay: 15s;">import React from 'react';</div>
<div class="floating-code" style="left: 50%; animation-delay: 20s;">docker build -t app .</div>
<div class="floating-code" style="left: 60%; animation-delay: 25s;">git commit -m "feat: add animation"</div>
<div class="floating-code" style="left: 70%; animation-delay: 30s;">kubectl apply -f deployment.yaml</div>
<div class="floating-code" style="left: 80%; animation-delay: 35s;">SELECT * FROM users;</div>
<div class="floating-code" style="left: 90%; animation-delay: 40s;">npm install</div>

<!-- HEADER -->
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=32&pause=1000&color=00F7FF&center=true&vCenter=true&width=900&lines=Hi,+I'm+Shivam+Dewangan;MERN+Stack+Developer+%26+DevOps+Engineer;Building+Scalable+Apps+%26+Automating+Pipelines">
</p>

---

<!-- ABOUT ME -->
<div class="section" style="padding:20px; border-radius:12px; margin-bottom:20px;">
<h2 style="color:#00c6ff;">About Me</h2>
<p style="color:#c0c0c0; line-height:1.6;">
I am <b>Shivam Dewangan</b>, a MERN Stack Developer & DevOps Engineer with a passion for building scalable, high-performance applications and automating end-to-end DevOps pipelines.<br><br>

<b>Full-Stack Development:</b> MongoDB, Express.js, React.js, Node.js (MERN)<br>
<b>Cloud Computing:</b> AWS & Azure<br>
<b>Containers & Orchestration:</b> Docker, Kubernetes, ArgoCD<br>
<b>CI/CD & DevOps:</b> Jenkins, GitHub Actions, Git<br>
<b>Linux & Scripting:</b> Bash, Python<br>

I focus on <b>cloud-native technologies</b>, modern development workflows, and continuous learning. I enjoy solving challenging problems and sharing knowledge with the community.
</p>
</div>

---

<!-- SOCIALS -->
<div class="section" style="padding:20px; border-radius:12px; margin-bottom:20px;">
<h2 style="color:#00c6ff;">Socials</h2>
<div style="display:flex; flex-wrap:wrap; gap:10px;">
  <a href="https://linkedin.com/in/shivamdewangan2005" target="_blank" style="padding:8px 15px; background:#0072B5; color:white; border-radius:6px; text-decoration:none;">LinkedIn</a>
  <a href="mailto:shivamdewangan310@gmail.com" style="padding:8px 15px; background:#D14836; color:white; border-radius:6px; text-decoration:none;">Email</a>
  <a href="https://github.com/shivam-dewangan" target="_blank" style="padding:8px 15px; background:#181717; color:white; border-radius:6px; text-decoration:none;">GitHub</a>
  <a href="https://twitter.com/shivam" target="_blank" style="padding:8px 15px; background:#1DA1F2; color:white; border-radius:6px; text-decoration:none;">Twitter</a>
</div>
</div>

---

<!-- TECH STACK -->
<div class="section" style="padding:20px; border-radius:12px; margin-bottom:20px;">
<h2 style="color:#00c6ff;">Tech Stack</h2>
<div style="display:flex; flex-wrap:wrap; gap:12px; margin-top:10px;">

  <!-- MERN -->
  <div style="background:linear-gradient(135deg,#00c6ff,#0072ff); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" width="20" height="20"> MongoDB</div>
  <div style="background:linear-gradient(135deg,#00c6ff,#0072ff); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" width="20" height="20"> Express.js</div>
  <div style="background:linear-gradient(135deg,#00c6ff,#0072ff); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="20" height="20"> React.js</div>
  <div style="background:linear-gradient(135deg,#00c6ff,#0072ff); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" width="20" height="20"> Node.js</div>
  <div style="background:linear-gradient(135deg,#00c6ff,#0072ff); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" width="20" height="20"> JavaScript</div>

  <!-- Cloud -->
  <div style="background:linear-gradient(135deg,#f7971e,#ffd200); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original.svg" width="20" height="20"> AWS</div>
  <div style="background:linear-gradient(135deg,#f7971e,#ffd200); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg" width="20" height="20"> Azure</div>
  <div style="background:linear-gradient(135deg,#f7971e,#ffd200); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vercel/vercel-original.svg" width="20" height="20"> Vercel</div>
  <div style="background:linear-gradient(135deg,#f7971e,#ffd200); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/netlify/netlify-original.svg" width="20" height="20"> Netlify</div>

  <!-- DevOps -->
  <div style="background:linear-gradient(135deg,#ff416c,#ff4b2b); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" width="20" height="20"> Docker</div>
  <div style="background:linear-gradient(135deg,#ff416c,#ff4b2b); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-plain.svg" width="20" height="20"> Kubernetes</div>
  <div style="background:linear-gradient(135deg,#ff416c,#ff4b2b); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/argocd/argocd-original.svg" width="20" height="20"> ArgoCD</div>
  <div style="background:linear-gradient(135deg,#ff416c,#ff4b2b); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jenkins/jenkins-original.svg" width="20" height="20"> Jenkins</div>
  <div style="background:linear-gradient(135deg,#ff416c,#ff4b2b); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" width="20" height="20"> GitHub Actions</div>
  <div style="background:linear-gradient(135deg,#ff416c,#ff4b2b); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" width="20" height="20"> Git</div>
  <div style="background:linear-gradient(135deg,#ff416c,#ff4b2b); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nginx/nginx-original.svg" width="20" height="20"> Nginx</div>

  <!-- Linux & Scripting -->
  <div style="background:linear-gradient(135deg,#2c3e50,#4ca1af); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" width="20" height="20"> Linux</div>
  <div style="background:linear-gradient(135deg,#2c3e50,#4ca1af); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" width="20" height="20"> Bash</div>
  <div style="background:linear-gradient(135deg,#2c3e50,#4ca1af); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="20" height="20"> Python</div>

  <!-- Databases & Others -->
  <div style="background:linear-gradient(135deg,#4CAF50,#2e7d32); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" width="20" height="20"> MySQL</div>
  <div style="background:linear-gradient(135deg,#4CAF50,#2e7d32); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jwt/jwt-original.svg" width="20" height="20"> JWT</div>
  <div style="background:linear-gradient(135deg,#4CAF50,#2e7d32); padding:10px 20px; border-radius:10px; color:white; display:flex; align-items:center; gap:8px;"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/socketio/socketio-original.svg" width="20" height="20"> Socket.io</div>

</div>
</div>

---

<!-- CERTIFICATIONS -->
<div class="section" style="padding:20px; border-radius:12px; margin-bottom:20px;">
<h2 style="color:#00c6ff;">Certifications</h2>
<ul style="color:#c0c0c0; line-height:1.8;">
  <li>Oracle Certified DevOps Professional</li>
  <li>Microsoft Azure Fundamentals (AZ-900)</li>
</ul>
</div>

---

<!-- GITHUB STATS -->
<div style="background-color:#1e1e2f; padding:20px; border-radius:12px; margin-bottom:20px;">
<h2 style="color:#00c6ff;">GitHub Stats</h2>
<p><img src="https://github-readme-stats.vercel.app/api?username=shivam-dewangan&theme=gruvbox&hide_border=true&include_all_commits=false&count_private=false"></p>
<p><img src="https://nirzak-streak-stats.vercel.app/?user=shivam-dewangan&theme=gruvbox&hide_border=true"></p>
<p><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=shivam-dewangan&theme=gruvbox&hide_border=true&include_all_commits=false&count_private=false&layout=compact"></p>
</div>

---

<!-- VISITOR COUNTER -->
<div class="section" style="padding:20px; border-radius:12px;">
<h2 style="color:#00c6ff;">Visitor Count</h2>
<p><a href="https://visitcount.itsvg.in"><img src="https://visitcount.itsvg.in/api?id=shivam-dewangan&icon=5&color=2" /></a></p>
</div>
