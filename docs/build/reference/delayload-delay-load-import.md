---
title: "/DELAYLOAD (Diff&#233;rer le chargement de l&#39;importation) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delayload"
  - "VC.Project.VCLinkerTool.DelayLoadDLLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYLOAD (option de l'éditeur de liens)"
  - "chargement différé de DLL, /DELAYLOAD (option)"
  - "DELAYLOAD (option de l'éditeur de liens)"
  - "-DELAYLOAD (option de l'éditeur de liens)"
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /DELAYLOAD (Diff&#233;rer le chargement de l&#39;importation)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYLOAD:dllname  
  
```  
  
## Paramètres  
 `dllname`  
 Le nom d'une DLL dont vous voulez différer le chargement.  
  
## Notes  
 Avec l'option \/DELAYLOAD, la DLL spécifiée par `dllname` n'est chargée que lors du premier appel du programme à une fonction contenue dans cette DLL.  Pour plus d'informations, consultez [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md).  Vous pouvez utiliser cette option autant de fois que nécessaire pour spécifier autant de DLL que vous voulez.  Vous devez utiliser Delayimp.lib au moment de lier votre programme, ou vous pouvez implémenter votre propre fonction d'assistance du chargement différé.  
  
 L'option [\/DELAY](../../build/reference/delay-delay-load-import-settings.md) permet de spécifier les options de liaison et de chargement pour chaque DLL chargée en différé.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le dossier **Éditeur de liens**, sélectionnez la page de propriétés **Entrée**.  
  
3.  Modifiez la propriété **Chargement différé des DLL**.  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)