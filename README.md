===============================
ComposTaZik - README (Terminal)
===============================

🎹 BIENVENUE DANS COMPOS TA ZIK
--------------------------------
Une application WPF de composition musicale moderne.
Compose, écoute, exporte, visualise... tout depuis ton PC.

👤 Connexion test :
--------------------
Email : test@zik.com  
Mot de passe : 1234

Utilise ce compte pour découvrir l'application sans créer de profil !

🧠 Développé par :
-------------------
- Koloina Rakotomavo
- Fatoumata Taran Diallo

📁 Installation (via ZIP)
---------------------------
1. 📦 Extraire le fichier ZIP du projet dans un dossier  


2. 🔧 Ouvrir un terminal dans le dossier extrait  
   (clic droit > "Ouvrir dans Terminal")

3. 🧰 Installer le SDK .NET 9 (si pas encore installé) :
---------------------------------------------------------
dotnet --version || winget install --id Microsoft.DotNet.SDK.9 --source winget

✅ Redémarre le terminal si tu viens de l’installer.

4. 🔧 Installer l'outil EF Core CLI :
--------------------------------------
dotnet tool install --global dotnet-ef

5. 📦 Ajouter les packages NuGet :
-----------------------------------
cd ComposTaZik  # entrer dans le dossier contenant ComposTaZik.csproj

dotnet add package Microsoft.EntityFrameworkCore.Sqlite  
dotnet add package Microsoft.EntityFrameworkCore.Tools  
dotnet add package CommunityToolkit.Mvvm  
dotnet add package NAudio  
dotnet add package xunit
dotnet add package Moq
dotnet add package Serilog.Sinks.File
dotnet add package Microsoft.Extensions.Configuration.Json
dotnet add package MahApps.Metro



6. 🔄 Restaurer et compiler :
------------------------------
dotnet restore ComposTaZik.csproj  
dotnet build ComposTaZik.csproj

7. 🗃️ Créer la base SQLite :
------------------------------
dotnet ef database update --project ComposTaZik.csproj

8. ▶️ Lancer l’application :
----------------------------
dotnet run --project ComposTaZik.csproj


🎵 Ce que tu peux faire dans l'app :
-------------------------------------

✅ Ajouter des notes musicales (clé de sol et clé de fa)  
✅ Choisir entre deux modes :
   - Mode Normal (une note par temps)
   - Mode Superposé (plusieurs notes = accord)  
✅ Dessiner ta partition ligne par ligne (4 mesures max par ligne)  
✅ Lire ta partition avec le moteur MIDI intégré (NAudio)  
✅ Sauvegarder une partition avec titre et compositeur  
✅ Recharger une partition depuis la base de données SQLite  
✅ Exporter ta partition en PDF

📌 Exemple pour créer un accord :
- Active le mode Superposé (bouton dans l'app)
- Clique sur plusieurs hauteurs à la même position horizontale
- Tu verras les notes empilées (superposition verticale)

📌 Exemple pour rejouer une partition :
- Clique sur “Voir les partitions”
- Sélectionne une partition
- Clique sur “Lire” ▶️

🗂️ Structure du projet :
--------------------------
- /Views : Fichiers XAML (UI)
- /ViewModels : Logique MVVM
- /Models : Entités musicales
- /Services : MIDI, PDF, gestion DB
- /Data : EF Core, DbContext
- /Assets : Images et sons

📍 Base de données locale :
----------------------------
Un fichier SQLite est automatiquement créé :
➡️ `ComposTaZik.db` (à la racine du projet)

---
