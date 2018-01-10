---
title: "L’instanciation du modèle de fonction | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41bf7f6ba3a2a17c6355ee9239cadb6e5014ee96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="function-template-instantiation"></a>Instanciation du modèle de fonction
Lorsqu'un modèle de fonction est appelé pour la première fois pour chaque type, le compilateur crée une instanciation. Chaque instanciation est une version de la fonction basée sur un modèle spécialisée pour le type. Cette instanciation est appelée chaque fois que la fonction est utilisée pour le type. Si vous avez plusieurs instanciations identiques, même dans différents modules, une seule copie de l'instanciation finira dans le fichier exécutable.  
  
 La conversion des arguments de fonction est autorisée dans les modèles de fonction pour toute paire argument-paramètre où le paramètre ne dépend pas d’un argument template.  
  
 Les modèles de fonction peuvent être instanciés de manière explicite en déclarant le modèle avec un type particulier comme argument. Par exemple, le code suivant est autorisé :  
  
```cpp
// function_template_instantiation.cpp  
template<class T> void f(T) { }  
  
// Instantiate f with the explicitly specified template.  
// argument 'int'  
//  
template void f<int> (int);  
  
// Instantiate f with the deduced template argument 'char'.  
template void f(char);  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles de fonctions](../cpp/function-templates.md)
