---
title: "Balises recommand&#233;es pour les commentaires de documentation (Visual&#160;C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Balises recommand&#233;es pour les commentaires de documentation (Visual&#160;C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur Visual C\+\+ traitera les commentaires de documentation dans votre code et crée un fichier .xdc pour chaque module \(compiland\), et xdcmake.exe traitera les fichiers .xdc à un fichier .xml.  Traiter le fichier .xml pour créer la documentation est un détail qui doit être implémenté à votre site.  
  
 Les balises sont traitées sur des éléments tels que des types et des membres de type.  
  
 Les balises doivent immédiatement précéder des types ou des membres.  
  
> [!NOTE]
>  Les commentaires de documentation ne peuvent pas être appliqués à un espace de noms ou en fonction hors de la définition de ligne pour les propriétés et les événements ; les commentaires de documentation doivent sur les déclarations de classe dans.  
  
 Le compilateur traite n'importe quelle balise représentant du XML correct.  Les balises suivantes fournissent les fonctionnalités couramment utilisées dans la documentation utilisateur :  
  
||||  
|-|-|-|  
|[\<c\>](../ide/c-visual-cpp.md)|[\<code\>](../ide/code-visual-cpp.md)|[\<example\>](../ide/example-visual-cpp.md)|  
|[\<exception\>](../ide/exception-visual-cpp.md)1|[\<include\>](../ide/include-visual-cpp.md)1|[\<list\>](../ide/list-visual-cpp.md)|  
|[\<para\>](../ide/para-visual-cpp.md)|[\<param\>](../ide/param-visual-cpp.md)1|[\<paramref\>](../ide/paramref-visual-cpp.md)1|  
|[\<permission\>](../ide/permission-visual-cpp.md)1|[\<remarks\>](../ide/remarks-visual-cpp.md)|[\<returns\>](../ide/returns-visual-cpp.md)|  
|[\<see\>](../ide/see-visual-cpp.md)1|[\<seealso\>](../ide/seealso-visual-cpp.md)1|[\<summary\>](../ide/summary-visual-cpp.md)|  
|[\<value\>](../ide/value-visual-cpp.md)|||  
  
 1.  Le compilateur vérifie la syntaxe.  
  
 Dans la version actuelle, le compilateur Visual C\+\+ ne prend pas `<paramref>`, une balise qui est prise en charge par d'autres compilateurs Visual Studio.  Visual C\+\+ peut prendre en charge `<paramref>` dans une version ultérieure.  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)