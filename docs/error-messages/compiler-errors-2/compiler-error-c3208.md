---
title: "Erreur du compilateur C3208 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3208"
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Erreur du compilateur C3208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : la liste de paramètres template pour le modèle de classe 'class' ne correspond pas à la liste de paramètres de modèle pour le paramètre template du modèle 'parameter'  
  
 Un paramètre template de modèle n’a pas le même nombre de paramètres template que le modèle de classe fourni.  
  
 L’exemple suivant génère l’erreur C3208 :  
  
```  
// C3208.cpp template <template <class T> class TT > int f(); template <class T1, class T2> struct S; template <class T1> struct R; int i = f<S>();   // C3208 // try the following line instead // int i = f<R>();  
```