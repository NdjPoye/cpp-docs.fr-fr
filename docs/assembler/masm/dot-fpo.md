---
title: ".FPO | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".FPO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".FPO directive"
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .FPO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de .FPO contrôle l'émission des enregistrements de débogage dans le segment ou à la section de .debug$F.  
  
## Syntaxe  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### Paramètres  
 `cdwLocals`  
 Nombre de variables locales, une valeur de 32 bits non signées.  
  
 `cdwParams`  
 Taille des paramètres dans des valeurs de type DWORD, une valeur de 16 bits non signées.  
  
 *cbProlog*  
 Nombre d'octets dans le code du prologue de fonction, une valeur de 8 bits non signées.  
  
 `cbRegs`  
 Registres de nombres enregistrés.  
  
 `fUseBP`  
 Indique si le registre EBP a été alloué.  0 ou 1.  
  
 *cbFrame*  
 indique le type de frame.  Consultez [FPO\_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352) pour plus d'informations.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)