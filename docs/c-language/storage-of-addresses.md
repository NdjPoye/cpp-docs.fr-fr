---
title: "Stockage des adresses | Microsoft Docs"
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
helpviewer_keywords: 
  - "adresses (C++), stockage de"
  - "stockage (C++), adresses"
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Stockage des adresses
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La quantité de stockage requis pour une adresse et la signification de l'adresse dépendent de l'implémentation du compilateur.  Les pointeurs vers des types différents ne sont pas garantis avoir la même longueur.  Par conséquent, **sizeof\(char \*\)** n'est pas nécessairement égal à **sizeof\(int \*\)**.  
  
 **Section spécifique à Microsoft**  
  
 Pour le compilateur C Microsoft, **sizeof\(char \*\)** est égal à **sizeof\(int \*\)**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Déclarations de pointeur](../c-language/pointer-declarations.md)