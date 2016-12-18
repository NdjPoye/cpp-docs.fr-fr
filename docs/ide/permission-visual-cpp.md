---
title: "&lt;permission&gt; (Visual C++) | Microsoft Docs"
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
  - "permission"
  - "<permission>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<permission> (balise XML C++)"
  - "permission (balise XML C++)"
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;permission&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<permission\> permet de documenter l'accès d'un membre.  <xref:System.Security.PermissionSet> vous permet de spécifier l'accès à un membre.  
  
## Syntaxe  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Paramètres  
 `member`  
 Référence à un membre ou un champ qu'il est possible d'appeler depuis l'environnement de compilation actuel.  Le compilateur vérifie que l'élément de code donné existe et traduit `member` dans le nom d'élément canonique dans le fichier de sortie XML.  Mettez le nom entre guillemets simples ou doubles.  
  
 Le compilateur émet un avertissement s'il ne trouve pas `member`.  
  
 Pour plus d'informations sur la création d'une référence cref à un type générique, consultez [\<see\>](../ide/see-visual-cpp.md).  
  
 `description`  
 Description de l'accès au membre.  
  
## Notes  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
 Le compilateur Visual C\+\+ tente de résoudre les références cref dans une série dans les commentaires de documentation.  Par conséquent, si vous utilisez les règles de recherche en C\+\+, un symbole est introuvable par le compilateur la référence est marquée comme non résolu.  Consultez [\<seealso\>](../ide/seealso-visual-cpp.md) pour plus d'informations.  
  
## Exemple  
  
```  
// xml_permission_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_permission_tag.dll  
using namespace System;  
/// Text for class TestClass.  
public ref class TestClass {  
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>  
   void Test() {}  
};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)