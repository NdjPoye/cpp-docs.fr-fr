---
title: Erreur du compilateur C3279 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3279
dev_langs: C++
helpviewer_keywords: C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4535edc3ccca0c5abd972e31ee7284fad7384c31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3279"></a>Erreur du compilateur C3279
les spécialisations partielles et explicites, ainsi que les instanciations explicites des modèles de classe déclarés dans l'espace de noms cli sont interdites  
  
 L’espace de noms `cli` est défini par Microsoft et contient des pseudo-modèles. Le compilateur Visual C++ n’autorise pas les spécialisations partielles et explicites définies par l’utilisateur, ni les instanciations de modèles de classe dans cet espace de noms.  
  
 L’exemple suivant génère l’erreur C3279 :  
  
```  
// C3279.cpp  
// compile with: /clr  
namespace cli {  
   template <> ref class array<int> {};   // C3279  
   template <typename T> ref class array<T, 2> {};   // C3279  
}  
```