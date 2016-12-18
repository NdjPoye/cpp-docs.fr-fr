---
title: "Erreur math&#233;matique M6111 | Microsoft Docs"
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
  - "M6111"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6111"
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur math&#233;matique M6111
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dépassement de capacité négatif de la pile  
  
 Une opération à virgule flottante s'est traduite par un dépassement de capacité par le bas de la pile sur l'émulateur ou le coprocesseur 8087\/287\/387.  
  
 Cette erreur est souvent due à un appel à une fonction de type `long double` qui ne retourne pas de valeur.  Par exemple, le code suivant génère cette erreur lors de la compilation et de l'exécution :  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 Le programme se termine par le code de sortie 139.