---
title: "&lt;include&gt; (Visual C++) | Microsoft Docs"
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
  - "include"
  - "<include>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<include> (balise XML C++)"
  - "include (balise XML C++)"
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;include&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<include\> permet de faire référence à des commentaires situés dans un autre fichier qui décrivent les types et membres dans votre code source.  Cette solution remplace celle consistant à placer des commentaires de documentation directement dans votre fichier de code source.  Par exemple, vous pouvez utiliser \<include\> pour insérer les commentaires standard « zones fixes » utilisés dans l'ensemble de votre équipe ou société.  
  
## Syntaxe  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### Paramètres  
 `filename`  
 Nom du fichier contenant la documentation.  Le nom du fichier peut être précisé par un chemin.  Mettez le nom entre guillemets simples ou doubles.  Le compilateur émet un avertissement s'il ne trouve pas `filename`.  
  
 `tagpath`  
 Une expression XPath valide qui sélectionne le nœud\- positionnement souhaité est contenu dans le fichier.  
  
 `name`  
 Dans la balise, spécificateur de nom précédant les commentaires ; `name` est associé à un `id`.  
  
 `id`  
 ID de la balise qui précède les commentaires.  Mettez le nom entre guillemets simples ou doubles.  
  
## Notes  
 La balise \<include\> utilise la syntaxe XML XPath.  Consultez la documentation de XPath pour les façons de personnaliser l' \<include\>.  
  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 Cet exemple fait appel à plusieurs fichiers.  Le premier fichier, qui utilise \<include\>, contient les commentaires de documentation suivants :  
  
```  
// xml_include_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_include_tag.dll  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />  
public ref class Test {  
   void TestMethod() {  
   }  
};  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />  
public ref class Test2 {  
   void Test() {  
   }  
};  
```  
  
 Le deuxième fichier, xml\_include\_tag.doc, contient les commentaires de documentation suivants :  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## Sortie du programme  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>t2</name>  
    </assembly>  
    <members>  
        <member name="T:Test">  
            <summary>  
The summary for this type.  
</summary>  
        </member>  
        <member name="T:Test2">  
            <summary>  
The summary for this other type.  
</summary>  
        </member>  
    </members>  
</doc>  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)