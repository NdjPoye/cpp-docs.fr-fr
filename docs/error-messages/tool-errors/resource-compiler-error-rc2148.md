---
title: "Erreur RC2148 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2148"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2148"
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur RC2148 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SUBLANGUAGE ID trop grand  
  
 La valeur de l'ID SUBLANGUAGE est en dehors de la plage autorisée.  
  
 L'instruction **LANGUAGE** doit utiliser la syntaxe suivante :  
  
 **LANGUAGE** *primary\_language\_ID*,*secondary\_language\_ID*  
  
 Les ID SUBLANGUAGE valides sont définis en tant que constantes **SUBLANG\_** dans le fichier WINNT.h.