---
title: Erreur du compilateur C2989 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2989
dev_langs: C++
helpviewer_keywords: C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: badfecd1c92b42a26682b714a16e24206ca05736
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2989"></a>Erreur du compilateur C2989
'classe' : type de classe a déjà été déclaré comme un type sans classe  
  
 La classe générique ou un modèle redéfinit une classe sans modèle ou non générique. Vérifiez les fichiers d’en-tête pour déterminer les conflits.  
  
 Si vous utilisez des spécialisations de modèle de classe partielle, consultez l’article Q240866 de la Base de connaissances.  
  
 L’exemple suivant génère l’erreur C2989 :  
  
```  
// C2989.cpp  
// compile with: /c  
class C{};  
  
template <class T>  
class C{};  // C2989  
class C2{};  
```  
  
 L’erreur C2989 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2989b.cpp  
// compile with: /clr /c  
ref class GC1;  
  
generic <typename T> ref class GC1;   // C2989  
template <typename T> ref class GC2;  
  
generic <typename T> ref class GC2;   // C2989  
generic <typename T> ref class GCb;  
template <typename T> ref class GC2;  
generic <typename T> ref class GCc;  
```