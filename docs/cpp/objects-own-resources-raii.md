---
title: "Objets possèdent des ressources (RAII) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05e23cc81666086bc34352a351ead8006b6c859f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="objects-own-resources-raii"></a>Ressources propres objets (RAII)
Assurez-vous que les ressources propres objets. Ce principe est également connu sous « resource acquisition is initialization » ou « RAII. »  
  
## <a name="example"></a>Exemple  
 Passez chaque objet « nouveau » comme un argument de constructeur à un autre objet nommé qui est propriétaire (presque toujours unique_ptr).  
  
```cpp  
void f() {  
    unique_ptr<widget> p( new widget() );  
    my_class x( new widget() );  
    // ...  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"  
```  
  
 Passez toujours immédiatement toute nouvelle ressource à un autre objet auquel il appartient.  
  
```cpp  
void g() {  
    other_class y( OpenFile() );  
    // ...  
} // automatic closing and release for file resource  
  // automatic exception safety, as if "finally { y.file.dispose(); }"  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Bienvenue dans C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Bibliothèque C++ standard](../standard-library/cpp-standard-library-reference.md)