---
title: "&lt;c&gt; (Visual C++) | Microsoft Docs"
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
  - "<c>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<c> (balise XML C++)"
  - "c (balise XML C++)"
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;c&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise d' \<c\> indique ce texte dans une description doit être marquée comme code.  Utilisez [\<code\>](../ide/code-visual-cpp.md) pour indiquer que plusieurs lignes constituent du code.  
  
## Syntaxe  
  
```  
<c>text</c>  
```  
  
#### Paramètres  
 `text`  
 Le texte que vous souhaitez désigner comme code.  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
  
```  
// xml_c_tag.cpp  
// compile with: /doc /LD  
// post-build command: xdcmake xml_c_tag.xdc  
  
/// Text for class MyClass.  
class MyClass {  
public:  
   int m_i;  
   MyClass() : m_i(0) {}  
  
   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.  
   /// </summary>  
   int MyMethod(MyClass * a) {  
      return a -> m_i;  
   }  
};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)