---
title: "&lt;param&gt; (Visual C++) | Microsoft Docs"
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
  - "param"
  - "<param>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<param> (balise XML C++)"
  - "param (balise XML C++)"
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;param&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<param\> doit être utilisée dans le commentaire pour une déclaration de méthode afin de décrire l'un des paramètres pour la méthode.  
  
## Syntaxe  
  
```  
<param name='name'>description</param>  
```  
  
#### Paramètres  
 `name`  
 Nom d'un paramètre de méthode.  Mettez le nom entre guillemets simples ou doubles.  Le compilateur émet un avertissement s'il ne trouve pas `name`.  
  
 `description`  
 Description du paramètre.  
  
## Notes  
 Le texte de la balise d' \<param\> s'affiche dans Intellisense, [Explorateur d'objets](http://msdn.microsoft.com/fr-fr/f89acfc5-1152-413d-9f56-3dc16e3f0470), et dans le rapport Web de commentaires du code.  
  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
  
```  
// xml_param_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_param_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <param name="Int1">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
   }  
};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)