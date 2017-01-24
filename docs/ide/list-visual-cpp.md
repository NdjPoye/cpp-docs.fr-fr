---
title: "&lt;list&gt; (Visual C++) | Microsoft Docs"
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
  - "list"
  - "<list>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<list> (balise XML C++)"
  - "list (balise XML C++)"
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;list&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le bloc \<listheader\> permet de définir la ligne de titre d'un tableau ou d'une liste de définitions.  Lorsque vous définissez un tableau, il suffit de fournir une entrée pour term dans le titre.  
  
## Syntaxe  
  
```  
<list type="bullet" | "number" | "table">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### Paramètres  
 `term`  
 Terme à définir, qui est défini dans `description`.  
  
 `description`  
 Élément d'une liste à puces ou numérotée, ou définition d'un `term`.  
  
## Notes  
 Chaque élément de la liste est spécifié par un bloc \<item\>.  Lorsque vous créez une liste de définitions, vous devez spécifier à la fois `term` et `description`.  Cependant, pour un tableau, une liste à puces ou une liste numérotée, il vous suffit de fournir une entrée pour `description`.  
  
 Une liste ou un tableau peut comporter autant de blocs \<item\> que nécessaire.  
  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
  
```  
// xml_list_tag.cpp  
// compile with: /doc /LD  
// post-build command: xdcmake xml_list_tag.dll  
/// <remarks>Here is an example of a bulleted list:  
/// <list type="bullet">  
/// <item>  
/// <description>Item 1.</description>  
/// </item>  
/// <item>  
/// <description>Item 2.</description>  
/// </item>  
/// </list>  
/// </remarks>  
class MyClass {};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)