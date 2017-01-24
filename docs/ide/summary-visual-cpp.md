---
title: "&lt;summary&gt; (Visual C++) | Microsoft Docs"
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
  - "<summary>"
  - "summary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<summary> (balise XML C++)"
  - "summary (balise XML C++)"
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;summary&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La balise \<summary\> doit être utilisée pour décrire un type ou un membre d'un type.  Utilisez [\<remarks\>](../ide/remarks-visual-cpp.md) pour ajouter des informations complémentaires à une description de type.  
  
## Syntaxe  
  
```  
<summary>description</summary>  
```  
  
#### Paramètres  
 `description`  
 Résumé de l'objet.  
  
## Notes  
 Le texte de la balise d' \<summary\> est la seule source d'informations sur le type dans Intellisense, et est également affiché dans [Explorateur d'objets](http://msdn.microsoft.com/fr-fr/f89acfc5-1152-413d-9f56-3dc16e3f0470) et dans le rapport Web de commentaires du code.  
  
 Compilez avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour traiter les commentaires de documentation et les placer dans un fichier.  
  
## Exemple  
  
```  
// xml_summary_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_summary_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>  
   /// <seealso cref="MyClass::MyMethod2"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void MyMethod2() {}  
};  
```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)