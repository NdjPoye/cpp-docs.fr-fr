---
title: "Aucune liaison | Microsoft Docs"
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
  - "liaison (C++), aucune"
  - "aucune liaison"
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Aucune liaison
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si une déclaration d'un identificateur dans un bloc n'inclut pas le spécificateur de classe de stockage `extern`, l'identificateur n'a aucune liaison et est propre à la fonction.  
  
 Les identificateurs suivants n'ont aucune liaison :  
  
-   Un identificateur déclaré comme autre chose qu'un objet ou une fonction  
  
-   un identificateur déclaré comme étant un paramètre de fonction  
  
-   Un identificateur de portée de bloc pour un objet déclaré sans spécificateur de classe de stockage `extern`  
  
 Si un identificateur n'a aucune liaison, une nouvelle déclaration du même nom \(dans un spécificateur de déclarateur ou de type\) au même niveau de portée génère une erreur de redéfinition de symbole.  
  
## Voir aussi  
 [Utilisation d'extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md)