---
title: "/APPCONTAINER (Application Windows Store) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /APPCONTAINER (Application Windows Store)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie si l'éditeur de liens crée une image exécutable qui doit être exécutée dans un conteneur d'application.  
  
## Syntaxe  
  
```  
/APPCONTAINER[:NO]  
```  
  
## Notes  
 Par défaut, \/APPCONTAINER est désactivé.  
  
 Cette option modifie un exécutable pour indiquer si l'application doit être exécutée dans l'environnement d'isolation de processus appcontainer.  Spécifiez \/APPCONTAINER pour une application qui doit s'exécuter dans l'environnement appcontainer \- par exemple, une application [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)]. \(L'option est définie automatiquement dans Visual Studio lorsque vous créez une application [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] à partir d'un modèle.\) Pour une application de bureau, spécifiez \/APPCONTAINER:NO ou omettez simplement l'option.  
  
 L'option \/APPCONTAINER a été introduite dans [!INCLUDE[win8](../../build/includes/win8_md.md)].  
  
### Pour définir cette option de l'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
5.  Dans **Options supplémentaires**, entrez `/APPCONTAINER` ou `/APPCONTAINER:NO`.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)