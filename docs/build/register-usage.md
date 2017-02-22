---
title: "Utilisation des Registres | Microsoft Docs"
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
ms.assetid: ce58e2cf-afd3-4068-980e-28a209298265
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Utilisation des Registres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'architecture [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] fournit 16 registres généraux \(ci\-après dénommés « registres d'entiers »\) en plus des 16 registres XMM\/YMM disponibles pour l'utilisation de nombres à virgule flottante.  Les registres volatils sont des registres de travail censés être détruits après un appel.  Les registres non volatils doivent conserver leurs valeurs tout au long d'un appel de fonction et être enregistrés par l'appelé s'il les utilise.  
  
 Le tableau suivant explique comment chaque registre est utilisé dans les appels de fonction :  
  
||||  
|-|-|-|  
|Registre|État|Utilisez|  
|RAX|Volatil|Registre des valeurs de retour|  
|RCX|Volatil|Premier argument entier|  
|RDX|Volatil|Deuxième argument entier|  
|R8|Volatil|Troisième argument entier|  
|R9|Volatil|Quatrième argument entier|  
|R10:R11|Volatil|Doit être conservé si nécessaire par l'appelant ; utilisé dans les instructions syscall\/sysret|  
|R12:R15|Non volatil|Doit être conservé par l'appelé|  
|RDI|Non volatil|Doit être conservé par l'appelé|  
|RSI|Non volatil|Doit être conservé par l'appelé|  
|RBX|Non volatil|Doit être conservé par l'appelé|  
|RBP|Non volatil|Peut être utilisé comme pointeur de frame ; doit être conservé par l'appelé|  
|RSP|Non volatil|Pointeur de pile|  
|XMM0, YMM0|Volatil|Premier argument FP ; premier argument de type vectoriel quand `__vectorcall` est utilisé|  
|XMM1, YMM1|Volatil|Deuxième argument FP ; deuxième argument de type vectoriel quand `__vectorcall` est utilisé|  
|XMM2, YMM2|Volatil|Troisième argument FP ; troisième argument de type vectoriel quand `__vectorcall` est utilisé|  
|XMM3, YMM3|Volatil|Quatrième argument FP ; quatrième argument de type vectoriel quand `__vectorcall` est utilisé|  
|XMM4, YMM4|Volatil|Doit être conservé si nécessaire par l'appelant ; cinquième argument de type vectoriel quand `__vectorcall` est utilisé|  
|XMM5, YMM5|Volatil|Doit être conservé si nécessaire par l'appelant ; sixième argument de type vectoriel quand `__vectorcall` est utilisé|  
|XMM6:XMM15, YMM6:YMM15|Non volatil \(XMM\), volatil \(moitié supérieure de YMM\)|Doit être conservé si nécessaire par l'appelé.  Les registres YMM doivent être conservés si nécessaire par l'appelant.|  
  
## Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)   
 [\_\_vectorcall](../cpp/vectorcall.md)