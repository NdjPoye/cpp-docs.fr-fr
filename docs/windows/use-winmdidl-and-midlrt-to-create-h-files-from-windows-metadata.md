---
title: "Comment&#160;: utiliser winmdidl.exe et midlrt.exe pour cr&#233;er les fichiers .h &#224; partir des m&#233;tadonn&#233;es Windows | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser winmdidl.exe et midlrt.exe pour cr&#233;er les fichiers .h &#224; partir des m&#233;tadonn&#233;es Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Winmdidl.exe et midlrt.exe permettent l'interaction de niveau COM entre le code C\+\+ natif et les composants Windows Runtime.  Winmdidl.exe prend comme entrée un fichier .winmd qui contient des métadonnées pour un composant Windows Runtime et génère un fichier IDL.  Midlrt.exe convertit ce fichier IDL en fichiers d'en\-tête que le code C\+\+ peut utiliser.  Les deux outils sont exécutés sur la ligne de commande.  
  
 Vous utilisez ces outils dans deux scénarios principaux :  
  
-   Création de fichiers d'en\-tête et IDL personnalisés pour qu'une application C\+\+ écrite à l'aide de la bibliothèque de modèles Windows Runtime \(WRL\) puisse utiliser un composant Windows Runtime personnalisé  
  
-   Génération de fichiers de proxy et stub pour les types d'événements définis par l'utilisateur dans un composant Windows Runtime  Pour plus d'informations, consultez [Déclenchement d'événements dans les composants Windows Runtime](../Topic/Raising%20Events%20in%20Windows%20Runtime%20Components.md).  
  
 Ces outils ne sont nécessaires que pour analyser les fichiers .winmd personnalisés.  Les fichiers .idl et .h pour les composants de système d'exploitation Windows sont automatiquement générés.  Par défaut dans [!INCLUDE[win81](../misc/includes/win81_md.md)], ils se trouvent dans \\Program Files \(x86\)\\Windows Kits\\8.1\\Include\\winrt\\.  
  
## Emplacement des outils  
 Par défaut dans [!INCLUDE[win81](../misc/includes/win81_md.md)], winmdidl.exe et midlrt.exe se trouvent dans C:\\Program Files \(x86\)\\Windows Kits\\8.1\\.  Des versions des outils sont également disponibles dans les dossiers \\bin\\x86\\ et \\bin\\x64\\.  
  
## Arguments de ligne de commande Winmdidl  
  
```  
  
Winmdidl.exe [/nologo] [/supressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile  
  
```  
  
 `/nologo`  
 Empêche l'affichage dans la console du message de copyright et du numéro de version winmdidl.  
  
 `/supressversioncheck`  
 Non utilisé.  
  
 `/time`  
 Affiche la durée totale d'exécution dans la sortie de la console.  
  
 \/outdir:\<rép\>  
 Spécifie un répertoire de sortie.  Si le chemin d'accès contient des espaces, placez\-le entre guillemets.  Le répertoire de sortie par défaut est *\<lecteur\>* :\\Users\\*\<nom\_utilisateur\>*\\AppData\\Local\\VirtualStore\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\.  
  
 `/banner:<file>`  
 Spécifie un fichier qui contient le texte personnalisé à faire figurer avant le message de copyright et le numéro de version winmdidl par défaut au début du fichier .idl généré.  Si le chemin d'accès contient des espaces, placez\-le entre guillemets.  
  
 `/utf8`  
 Le format du fichier sera UTF\-8.  
  
 `Winmdfile`  
 Nom du fichier .winmd à analyser.  Si le chemin d'accès contient des espaces, placez\-le entre guillemets.  
  
## Arguments de ligne de commande Midlrt  
 Consultez [Composants MIDLRT et Windows Runtime](http://msdn.microsoft.com/library/windows/desktop/hh869900\(v=vs.85\).aspx).  
  
## Exemples  
 L'exemple suivant montre une commande winmdidl à une invite de commandes Visual Studio x86.  Elle spécifie un répertoire de sortie et un fichier qui contient le texte de bannière spécial à ajouter au fichier .idl généré.  
  
 **C:\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\>winmdidl \/nologo \/outdir:c:\\users\\giraffe\\documents\\ \/banner:c:\\users\\giraffe\\documents\\banner.txt "C:\\Users\\giraffe\\Documents\\Visual Studio 2013\\Projects\\Test\_for\_winmdidl\\Debug\\Test\_for\_winmdidl\\test\_for\_winmdidl.winmd"**  
  
 L'exemple suivant illustre l'affichage de la console à partir de winmdidl qui indique que l'opération a réussi.  
  
 **Generating c:\\users\\giraffe\\documents\\\\Test\_for\_winmdidl.idl**  
  
 Ensuite, midlrt est exécuté sur le fichier IDL généré.  Notez que l'argument **metadata\_dir** est spécifié après le nom du fichier .idl.  Le chemin d'accès de \\WinMetadata\\ est obligatoire ; il s'agit de l'emplacement de windows.winmd.  
  
 **C:\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\> midlrt "c:\\users\\mblome\\documents\\test\_for\_winmdidl.idl" \/metadata\_dir "C:\\Windows\\System32\\WinMetadata"**  
  
## Notes  
 Le fichier de sortie d'une opération winmdidl a le même nom que le fichier d'entrée, mais porte l'extension de nom de fichier .idl.  
  
 Si vous développez un composant Windows Runtime qui est accessible à partir de la bibliothèque WRL, vous pouvez spécifier que winmdidl.exe et midlrt.exe s'exécutent en guise d'étapes post\-builds pour que les fichiers .idl et .h soient générés sur chaque build.  Pour obtenir un exemple, consultez [Déclenchement d'événements dans les composants Windows Runtime](../Topic/Raising%20Events%20in%20Windows%20Runtime%20Components.md).