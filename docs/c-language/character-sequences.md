---
title: "S&#233;quences de caract&#232;res | Microsoft Docs"
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
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;quences de caract&#232;res
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** Mappage des séquences de caractères de fichier source  
  
 Les instructions de préprocesseur utilisent le même jeu de caractères que les instructions de fichier source, sauf que les séquences d'échappement ne sont pas prises en charge.  
  
 Ainsi, pour spécifier le chemin d'accès d'un fichier Include, utilisez une seule barre oblique inverse :  
  
```  
#include "path1\path2\myfile"  
```  
  
 Dans le code source, deux barres obliques inverses sont nécessaires :  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## Voir aussi  
 [Directives de prétraitement](../c-language/preprocessing-directives.md)