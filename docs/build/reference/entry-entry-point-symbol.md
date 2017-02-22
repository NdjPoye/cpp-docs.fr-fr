---
title: "/ENTRY (Symbole de point d&#39;entr&#233;e) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/entry"
  - "VC.Project.VCLinkerTool.EntryPointSymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ENTRY (option de l'éditeur de liens)"
  - "ENTRY (option de l'éditeur de liens)"
  - "-ENTRY (option de l'éditeur de liens)"
  - "adresse de départ"
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ENTRY (Symbole de point d&#39;entr&#233;e)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ENTRY:function  
```  
  
## Notes  
 où :  
  
 *fonction*  
 désigne une fonction spécifiant l'adresse de départ définie par l'utilisateur d'un fichier .exe ou d'une DLL.  
  
## Notes  
 L'option \/ENTRY spécifie une fonction de point d'entrée comme adresse de départ d'un fichier .exe ou DLL.  
  
 La fonction doit être définie suivant la convention d'appel `__stdcall`.  Les paramètres et la valeur de retour dépendent du programme s'il est une application console, une application de fenêtres ou une DLL.  Il est recommandé de laisser l'éditeur de liens définir le point d'entrée pour que la bibliothèque Runtime C soit initialisée correctement et que les constructeurs C\+\+ d'objets statiques soient exécutés.  
  
 Par défaut, l'adresse de départ est un nom de fonction issu de la bibliothèque Runtime C.  L'éditeur de liens la sélectionne d'après les attributs du programme, comme indiqué dans le tableau suivant.  
  
|Nom de la fonction|Par défaut|  
|------------------------|----------------|  
|**mainCRTStartup** \(ou **wmainCRTStartup**\)|Une application utilisant \/SUBSYSTEM:**CONSOLE ;** appelle la fonction **main** \(ou **wmain**\).|  
|**WinMainCRTStartup** \(ou **wWinMainCRTStartup**\)|Une application utilisant \/SUBSYSTEM:**WINDOWS ;** appelle la fonction `WinMain` \(ou **wWinMain**\), qui doit être définie avec `__stdcall`|  
|**\_DllMainCRTStartup**|Une DLL ; appelle la fonction `DllMain`, qui doit être définie avec `__stdcall`, si elle existe.|  
  
 Si l'option [\/DLL](../../build/reference/dll-build-a-dll.md) ou [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) n'est pas spécifiée, l'éditeur de liens sélectionne un sous\-système et un point d'entrée selon que **main** ou `WinMain` est défini.  
  
 Les fonctions **main**, `WinMain` et `DllMain` sont les trois formes du point d'entrée défini par l'utilisateur.  
  
 Lors de la création d'une image managée, la fonction spécifiée avec \/ENTRY doit avoir une signature de \(LPVOID *var1*, DWORD *var2*, LPVOID *var3*\).  
  
 Pour plus d'informations sur la définition de votre propre point d'entrée DllMain, consultez [Comportement de la bibliothèque runtime](../../build/run-time-library-behavior.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Point d'entrée**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)