---
title: "/DELAY (Param&#232;tres d&#39;importation &#224; chargement diff&#233;r&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delay"
  - "VC.Project.VCLinkerTool.DelayNoBind"
  - "VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL"
  - "VC.Project.VCLinkerTool.DelayUnload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY (option de l'éditeur de liens)"
  - "DELAY (option de l'éditeur de liens)"
  - "-DELAY (option de l'éditeur de liens)"
  - "chargement différé de DLL, /DELAY (option)"
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DELAY (Param&#232;tres d&#39;importation &#224; chargement diff&#233;r&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## Notes  
 L'option \/DELAY contrôle le [chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md) des DLL :  
  
-   Le qualificateur UNLOAD indique à la fonction d'assistance de chargement différé de prendre en charge le déchargement explicite de la DLL.  La table IAT \(Import Address Table\) est réinitialisée à sa forme d'origine, ce qui invalide les pointeurs IAT et entraîne leur remplacement.  
  
     Si vous ne sélectionnez pas UNLOAD, tout appel à [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) échouera.  
  
-   Le qualificateur NOBIND indique à l'éditeur de liens de ne pas inclure dans l'image finale de table IAT pouvant être liée.  L'option par défaut consiste à créer la table IAT pouvant être liée pour les DLL chargées en différé.  L'image obtenue ne peut pas être liée statiquement.  \(Les images avec des tables IAT pouvant être liées sont susceptibles d'être liées statiquement avant leur exécution.\) Voir [\/BIND](../../build/reference/bind.md).  
  
     Si la DLL est liée, la fonction d'assistance essaie d'utiliser les informations liées au lieu d'appeler [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) sur chacune des importations référencées.  Si l'horodatage ou l'adresse préférée ne correspondent pas à ceux de la DLL chargée, la fonction d'assistance suppose que la table IAT liée est obsolète et continuera comme si la table IAT liée n'existe pas.  
  
     NOBIND augmente la taille de votre image de programme mais peut réduire le temps de chargement de la DLL.  Si vous n'avez pas l'intention de lier la DLL, NOBIND empêchera la création de la table IAT liée.  
  
 Pour spécifier des DLL pour différer le chargement, utilisez l'option [\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez **Propriétés de configuration** et **Éditeur de liens**, puis sélectionnez **Avancé**.  
  
3.  Modifiez la propriété **Chargement différé des DLL**.  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)