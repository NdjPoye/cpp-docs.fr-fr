---
title: "Personnalisation des Assistants C++ &#224; l&#39;aide des fonctions JScript classiques | Microsoft Docs"
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
  - "méthodes JScript de l'Assistant, créer des Assistants C++"
ms.assetid: c602978f-a2c4-462f-85c3-50b5897bec46
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Personnalisation des Assistants C++ &#224; l&#39;aide des fonctions JScript classiques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez un projet d'Assistant avec l'[Assistant personnalisé](../ide/creating-a-custom-wizard.md), votre projet inclut Common.js.  Si vous spécifiez une interface utilisateur pour votre Assistant, le projet contient également des pages HTML qui spécifient le langage de script JScript et incluent le fichier Common.js, comme suit :  
  
```  
<SCRIPT ID="INCLUDE_COMMON" LANGUAGE ="JSCRIPT"></SCRIPT>  
```  
  
 L'Assistant crée également un fichier unique appelé Default.js.  Vous pouvez personnaliser votre propre JScript fonctionne dans Default.js.  Consultez [Le fichier Jscript](../ide/jscript-file.md) pour plus d'informations.  
  
 Common.js contient des fonctions que vous pouvez appeler depuis les pages HTML de chaque Assistant et depuis Default.js.  Si vous avez les mêmes fonctions que vous aimeriez utiliser dans différents Assistants, vous pouvez placer ces fonctions dans Common.js.  
  
## Voir aussi  
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)