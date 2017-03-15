---
title: "&lt;seealso&gt; (Visual C++) | Microsoft Docs"
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
  - "<seealso>"
  - "seealso"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<seealso> (balise XML C++)"
  - "seealso (balise XML C++)"
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;seealso&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<seealso\> permet de spécifier le texte que vous souhaitez voir apparaître dans une section « Voir aussi ».  Utilisez [\<see\>](../ide/see-visual-cpp.md) pour spécifier un lien à partir de l'intérieur du texte.  
  
## Syntaxe  
  
```  
<seealso cref="member"/>  
```  
  
#### Paramètres  
 `member`  
 Référence à un membre ou un champ qu'il est possible d'appeler depuis l'environnement de compilation actuel.  Mettez le nom entre guillemets simples ou doubles.  
  
 Le compilateur vérifie que l'élément de code spécifié existe et résout `member` au nom de l'élément dans la sortie XML.  Le compilateur émet un avertissement s'il ne trouve pas `member`.  
  
 Pour plus d'informations sur la création d'une référence cref à un type générique, consultez [\<see\>](../ide/see-visual-cpp.md).  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
 Consultez [\<summary\>](../ide/summary-visual-cpp.md) pour obtenir un exemple d'utilisation \<seealso\>.  
  
 Le compilateur Visual C\+\+ tente de résoudre les références cref dans une série dans les commentaires de documentation.  Par conséquent, si vous utilisez les règles de recherche en C\+\+, un symbole est introuvable par le compilateur la référence est marquée comme non résolu.  
  
## Exemple  
 Dans l'exemple suivant, un symbole non résolu est référencé dans un cref.  Le commentaire XML pour le cref à B::Test sera `<seealso cref="!:B::Test" />`, alors que la référence à A::Test est `<seealso cref="M:A.Test" />`de forme correcte.  
  
```  
// xml_seealso_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_seealso_tag.dll  
  
/// Text for class A.  
public ref struct A {  
   /// <summary><seealso cref="A::Test"/>  
   /// <seealso cref="B::Test"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void Test() {}  
};  
  
/// Text for class B.  
public ref struct B {  
   void Test() {}  
};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)