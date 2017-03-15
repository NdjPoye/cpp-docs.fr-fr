---
title: "Naked (C) | Microsoft Docs"
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
helpviewer_keywords: 
  - "code d'épilogue"
  - "naked (mot clé) (C)"
  - "naked (mot clé) (C), attribut de classe de stockage"
  - "code du prologue"
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Naked (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 L'attribut de classe de stockage naked est une extension spécifique à Microsoft pour le langage C.  Le compilateur génère un code sans code de prologue ni d'épilogue pour les fonctions déclarées avec l'attribut de classe de stockage naked.  Les fonctions naked sont utiles lorsque vous devez écrire vos propres séquences de code de prologue\/épilogue à l'aide de code assembleur inline.  Les fonctions naked sont utiles pour écrire des pilotes de périphériques virtuels.  
  
 Pour obtenir des informations spécifiques sur l'utilisation de l'attribut naked, consultez [Fonctions naked](../c-language/naked-functions.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Attributs étendus de classe de stockage C](../c-language/c-extended-storage-class-attributes.md)