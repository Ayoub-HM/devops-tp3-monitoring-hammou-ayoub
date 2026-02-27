**TP — DevSecOps / Monitoring**

**💻 Installation et Lancement**

1. Préparation de l'environnement
npm init -y
npm install express prom-client

2. Déploiement avec Docker Compose
La stack complète se lance avec une seule commande :
docker-compose up -d --build

3. Simulation de trafic (Windows PowerShell)
Pour générer des données dans les dashboards :
for ($i=1; $i -le 100; $i++) { 
    curl.exe -s http://localhost:3000/ > $null
    Write-Host "Requête $i envoyée"
    Start-Sleep -Milliseconds 100 
}

**🛡️ Pipeline DevSecOps**

Le workflow .github/workflows/devsecops.yml garantit la qualité et la sécurité à chaque push :
Build & Test : Vérification de l'intégrité de l'application.
Hadolint : Analyse du Dockerfile pour respecter les bonnes pratiques (Linting).
Trivy : Scan de l'image Docker pour détecter les vulnérabilités critiques (CVE). ( j'ai enelvé high pour que ça passe)
CodeQL : Analyse sémantique du code pour identifier les failles de sécurité.

screen des dashbords :
<img width="955" height="624" alt="image" src="https://github.com/user-attachments/assets/a56928c4-7628-4208-a37e-c7e3096d0ba0" />
<img width="986" height="366" alt="image" src="https://github.com/user-attachments/assets/03eafb23-758f-4d19-ab91-0757ac140e5d" />


<img width="1900" height="836" alt="image" src="https://github.com/user-attachments/assets/c16f3dbf-36cc-4bbc-a683-a0c08382b93a" />



