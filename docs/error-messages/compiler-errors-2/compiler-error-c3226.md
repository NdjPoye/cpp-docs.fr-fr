---
title: Erreur du compilateur C3226 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3226
dev_langs: C++
helpviewer_keywords: C3226
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a10e9ba474941fdb9ed99ed206d85dacf6c9ff50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3226"></a>Erreur du compilateur C3226
Une déclaration de modèle n'est pas autorisée dans une déclaration générique  
  
 Utilisez une déclaration générique à l’intérieur d’une classe générique.  
  
 L’exemple suivant génère l’erreur C3226 :  
  
```  
// C3226.cpp  
// compile with: /clr  
generic <class T>  
ref class C {  
   template <class T1>   // C3226  
   ref struct S1 {};  
};  
```  
  
 L’exemple suivant illustre une résolution possible :  
  
```  
// C3226b.cpp  
// compile with: /clr /c  
generic <class T>  
ref class C {  
   generic <class T1>  
   ref struct S1 {};  
};  
```