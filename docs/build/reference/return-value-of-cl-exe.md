---
title: "Valeur de retour de cl.exe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, valeur de retour"
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Valeur de retour de cl.exe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cl.exe retourne zéro en cas de réussite \(aucune erreur\) et une valeur différente de zéro dans les autres cas.  
  
 La valeur de retour de cl.exe peut être utile si vous compilez à partir d'un fichier script, powershell, .cmd ou .bat.  Il est recommandé de capturer la sortie du compilateur afin de pouvoir résoudre les erreurs ou avertissements éventuels.  
  
 Il y a trop de codes de sortie d'erreur possibles pour que cl.exe puisse tous les répertorier.  Vous pouvez rechercher un code d'erreur dans les fichiers winerror.h ou ntstatus.h inclus dans le Kit de développement logiciel Windows, dans le répertoire %ProgramFiles\(x86\)%\\Windows Kits\\`version`\\Include\\shared\\.  Les codes d'erreur retournés au format décimal doivent être convertis au format hexadécimal pour la recherche.  Par exemple, le code d'erreur \-1073741620 converti au format hexadécimal correspond à 0xC00000CC.  Cette erreur se trouve dans ntstatus.h, où le message correspondant est « La ressource partagée spécifiée sur le serveur distant est introuvable. » Pour obtenir une liste téléchargeable des codes d'erreur Windows, consultez [&#91;MS\-ERREF&#93;: Windows Error Codes](http://msdn.microsoft.com/fr-fr/1bc92ddf-b79e-413c-bbaa-99a5281a6c90).  
  
 Vous pouvez également utiliser l'utilitaire de recherche d'erreurs dans Visual Studio pour connaître la signification d'un message d'erreur du compilateur.  Dans l'interpréteur de commandes de Visual Studio, entrez **errlook.exe** pour démarrer l'utilitaire. À défaut, dans l'IDE de Visual Studio, dans la barre de menus, choisissez **Outils**, **Errlook \- Recherche d'erreurs**.  Entrez la valeur d'erreur pour rechercher le texte descriptif associé à l'erreur.  Pour plus d'informations, consultez [Référence d'ERRLOOK](../../build/reference/errlook-reference.md).  
  
## Notes  
 Vous trouverez ci\-dessous un exemple de fichier .bat qui utilise la valeur de retour de cl.exe.  
  
```  
echo off  
cl /W4 t.cpp  
@if ERRORLEVEL == 0 (  
   goto good  
)  
  
@if ERRORLEVEL != 0 (  
   goto bad  
)  
  
:good  
   echo "clean compile"  
   echo %ERRORLEVEL%  
   goto end  
  
:bad  
   echo "error or warning"  
   echo %ERRORLEVEL%  
   goto end  
  
:end  
```  
  
## Voir aussi  
 [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md)