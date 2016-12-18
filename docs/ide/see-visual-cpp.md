---
title: "&lt;see&gt; (Visual C++) | Microsoft Docs"
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
  - "<see>"
  - "see"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<see> (balise XML C++)"
  - "see (balise XML C++)"
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;see&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<see\> permet de spécifier un lien à partir de l'intérieur du texte.  Utilisation [\<seealso\>](../ide/seealso-visual-cpp.md) d'indiquer le texte que vous souhaitez afficher dans une section de voir aussi.  
  
## Syntaxe  
  
```  
<see cref="member"/>  
```  
  
#### Paramètres  
 `member`  
 Référence à un membre ou un champ qu'il est possible d'appeler depuis l'environnement de compilation actuel.  Mettez le nom entre guillemets simples ou doubles.  
  
 Le compilateur vérifie que l'élément de code spécifié existe et résout `member` au nom de l'élément dans la sortie XML.  Le compilateur émet un avertissement s'il ne trouve pas `member`.  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
 Consultez l' [\<summary\>](../ide/summary-visual-cpp.md) pour obtenir un exemple d'utilisation \<see\>.  
  
 Le compilateur Visual C\+\+ tente de résoudre les références cref dans une série dans les commentaires de documentation.  Par conséquent, si vous utilisez les règles de recherche en C\+\+, un symbole est introuvable par le compilateur la référence est marquée comme non résolu.  Consultez [\<seealso\>](../ide/seealso-visual-cpp.md) pour plus d'informations.  
  
## Exemple  
 L'exemple suivant montre comment vous pouvez faire référence cref à un type générique, tels que, le compilateur résout la référence.  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)