---
title: '&lt;valeur&gt; (Visual C++) | Documents Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- value
- <value>
dev_langs:
- C++
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d1621a8251bddb1d4c7d1bf3f00c4ccf3ea5242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ltvaluegt-visual-c"></a>&lt;valeur&gt; (Visual C++)
Le \<valeur > balise vous permet de décrire une propriété et des méthodes d’accesseur de propriété. Remarquez que lorsque vous ajoutez une propriété avec un Assistant code dans l’environnement de développement intégré Visual Studio, un [ \<Résumé >](../ide/summary-visual-cpp.md) balise pour la nouvelle propriété. Vous devez ensuite ajouter manuellement une balise \<value> pour décrire la valeur représentée par la propriété.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `property-description`  
 Description de la propriété.  
  
## <a name="remarks"></a>Notes  
 Compilez avec [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour placer les commentaires de documentation dans un fichier en vue de les traiter.  
  
## <a name="example"></a>Exemple  
  
```  
// xml_value_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_value_tag.dll  
using namespace System;  
/// Text for class Employee.  
public ref class Employee {  
private:  
   String ^ name;  
   /// <value>Name accesses the value of the name data member</value>  
public:  
   property String ^ Name {  
      String ^ get() {  
         return name;   
      }  
      void set(String ^ i) {  
         name = i;  
      }  
   }  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)