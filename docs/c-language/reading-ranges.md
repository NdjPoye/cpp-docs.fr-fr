---
title: "Lecture des plages | Microsoft Docs"
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
  - "C"
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Lecture des plages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.9.6.2** La traduction d'un tiret \(–\) qui n'est ni le premier ni le dernier caractère de la scanlist pour la conversion % \[ dans la fonction `fscanf`  
  
 La ligne suivante  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 lit tout nombre de caractères dans la plage A\-Z dans la chaîne vers laquelle pointe `strptr`.  
  
## Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)