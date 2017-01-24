---
title: "Erreur du compilateur C2026 | Microsoft Docs"
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
  - "C2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2026"
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

chaîne trop grande, caractères de fin tronqués  
  
 La chaîne était plus longue que la limite de 16380 caractères codés sur un seul octet.  
  
 Avant concaténation des chaînes adjacentes, une chaîne ne peut pas dépasser 16380 caractères codés sur un seul octet.  
  
 Une chaîne Unicode d'environ la moitié de cette longueur générerait également cette erreur.  
  
 La définition d'une chaîne comme suit génère C2026 :  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Vous pourriez la fractionner comme suit :  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Il peut être utile de stocker des littéraux de chaîne de taille exceptionnelle \(32 Ko ou plus\) dans une ressource personnalisée ou dans un fichier externe.  Pour plus d'informations, consultez [Création d'une ressource personnalisée ou d'une ressource données](../../mfc/creating-a-new-custom-or-data-resource.md).