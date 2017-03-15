---
title: "&lt;para&gt; (Visual C++) | Microsoft Docs"
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
  - "<para>"
  - "para"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<para> (balise XML C++)"
  - "para (balise XML C++)"
ms.assetid: 35f2a1b3-bc14-4f13-bcb0-c39ccbf74d59
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;para&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<para\> est à utiliser à l'intérieur d'une autre balise, telle que [\<summary\>](../ide/summary-visual-cpp.md), [\<remarks\>](../ide/remarks-visual-cpp.md) ou [\<returns\>](../ide/returns-visual-cpp.md), et vous permet de structurer le texte.  
  
## Syntaxe  
  
```  
<para>content</para>  
```  
  
#### Paramètres  
 `content`  
 Texte du paragraphe.  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
 Pour obtenir un exemple d'utilisation de \<para\>, consultez [\<summary\>](../ide/summary-visual-cpp.md).  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)