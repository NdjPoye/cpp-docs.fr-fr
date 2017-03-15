---
title: "&lt;value&gt; (Visual Basic) | Microsoft Docs"
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
  - "value"
  - "<value>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<value> (balise XML C++)"
  - "<value> (balise XML C++)"
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;value&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise d' \<value\> vous permet de décrire une propriété et des méthodes d'accesseur de propriété.  Notez que lorsque vous ajoutez une propriété avec un Assistant Code dans l'environnement de développement intégré \(IDE\) de Visual Studio, il ajoute une balise d' [\<summary\>](../ide/summary-visual-cpp.md) pour la nouvelle propriété.  Vous devez ensuite ajouter manuellement une balise \<value\> pour décrire la valeur représentée par la propriété.  
  
## Syntaxe  
  
```  
<value>property-description</value>  
```  
  
#### Paramètres  
 `property-description`  
 Description de la propriété.  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
  
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
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)