---
title: "Erreur du compilateur C3813 | Microsoft Docs"
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
  - "C3813"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3813"
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

une déclaration de propriété ne peut figurer qu'au sein d'une définition de type managé ou WinRT  
  
 Une [propriété](../../misc/property.md) peut uniquement être déclarée au sein d'un type managé ou Windows Runtime.  Les types natifs ne prennent pas en charge le mot clé `property`.  
  
 L'exemple suivant génère l'erreur C3813 et montre comment la corriger :  
  
```  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```