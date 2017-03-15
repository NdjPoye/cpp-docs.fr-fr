---
title: "&lt;example&gt; (Visual C++) | Microsoft Docs"
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
  - "<example>"
  - "example"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<example> (balise XML C++)"
  - "example (balise XML C++)"
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;example&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<example\> vous permet de spécifier un exemple d'utilisation d'une méthode ou de tout autre membre de bibliothèque.  En général, cela comporterait également l'utilisation de la balise d' [\<code\>](../ide/code-visual-cpp.md) .  
  
## Syntaxe  
  
```  
<example>description</example>  
```  
  
#### Paramètres  
 `description`  
 Description de l'exemple de code.  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
  
```  
// xml_example_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_example_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <summary>  
   /// GetZero method  
   /// </summary>  
   /// <example> This sample shows how to call the GetZero method.  
   /// <code>  
   /// int main()   
   /// {  
   ///    return GetZero();  
   /// }  
   /// </code>  
   /// </example>  
   static int GetZero() {  
      return 0;  
   }  
};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)