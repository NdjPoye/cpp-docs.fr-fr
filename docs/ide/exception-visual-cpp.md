---
title: "&lt;exception&gt; (Visual&#160;C&#176;++) | Microsoft Docs"
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
  - "exception"
  - "<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<exception> (balise XML C++)"
  - "exception (balise XML C++)"
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;exception&gt; (Visual&#160;C&#176;++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<exception\> permet de spécifier les exceptions qui peuvent être levées.  Cette balise est appliquée à une définition de méthode.  
  
## Syntaxe  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Paramètres  
 `member`  
 Référence à une exception disponible dans l'environnement de compilation en cours.  À l'aide de les règles de recherche de nom, le compilateur vérifie que l'exception donnée existe, et traduit `member` le nom d'élément canonique dans la sortie XML.  Le compilateur émet un avertissement s'il ne trouve pas `member`.  
  
 Mettez le nom entre guillemets simples ou doubles.  
  
 Pour plus d'informations sur la création d'une référence cref à un type générique, consultez [\<see\>](../ide/see-visual-cpp.md).  
  
 `description`  
 Description.  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
 Le compilateur Visual C\+\+ tente de résoudre les références cref dans une série dans les commentaires de documentation.  Par conséquent, si vous utilisez les règles de recherche en C\+\+, un symbole est introuvable par le compilateur la référence est marquée comme non résolu.  Consultez [\<seealso\>](../ide/seealso-visual-cpp.md) pour plus d'informations.  
  
## Exemple  
  
```  
// xml_exception_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_exception_tag.dll  
using namespace System;  
  
/// Text for class EClass.  
public ref class EClass : public Exception {  
   // class definition ...  
};  
  
/// <exception cref="System.Exception">Thrown when... .</exception>  
public ref class TestClass {  
   void Test() {  
      try {  
      }  
      catch(EClass^) {  
      }  
   }  
};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)