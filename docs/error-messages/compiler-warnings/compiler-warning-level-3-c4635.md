---
title: "Avertissement du compilateur (niveau&#160;3) C4635 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4635"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4635"
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau&#160;3) C4635
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cible de commentaire de document XML : code XML incorrect : raison  
  
 Le compilateur a détecté un problème avec les balises XML.  Corrigez le problème et recompilez.  
  
 L’exemple suivant génère l’avertissement C4635 :  
  
```  
// C4635.cpp // compile with: /doc /clr /W3 /c /// <summary> /// The contents of the folder have changed. /// <summary/>   // C4635 // try the following line instead // /// </summary> public ref class Test {};  
```  
  
 Notez que la sortie de cet exemple indique : **La balise de fin 'member' ne correspond pas à la balise de début 'summary'.**  
  
 Le problème avec cet exemple est que la balise de fin \<summary\> est mal formée. Le compilateur ne la reconnaît pas comme balise de fin \<summary\>.  La balise \<member\> est incorporée dans le fichier .xdc par le compilateur dans chaque compilation \/doc.  Le problème ici est que la balise de fin \<\/member\> ne correspond pas à la balise de début précédente traitée par le compilateur \(\<summary\>\).