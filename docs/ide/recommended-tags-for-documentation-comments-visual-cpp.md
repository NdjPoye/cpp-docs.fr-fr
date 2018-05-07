---
title: Balises recommandées pour commentaires de Documentation (Visual C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b25ad029a59c4b23bcab093b3742f16f7ca9175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>Étiquettes recommandées pour les commentaires de documentation (Visual C++)
Le compilateur Visual C++ traite les commentaires de documentation dans votre code et crée un fichier .xdc pour chaque compiland et xdcmake.exe traite les fichiers .xdc dans un fichier .xml. Traitement du fichier .xml pour créer une documentation est un détail qui doit être implémentée sur votre site.  
  
 Les balises sont traitées sur les constructions telles que les types et membres de type.  
  
 Balises doivent précéder immédiatement les types ou membres.  
  
> [!NOTE]
>  Commentaires de documentation ne peut pas être appliqués à un espace de noms ou dans en dehors de la définition de ligne pour les propriétés et événements ; commentaires de documentation doivent sur les déclarations de classe.  
  
 Le compilateur traite toute balise représentant du code XML correct. Les balises suivantes fournissent des fonctionnalités couramment utilisées dans la documentation de l’utilisateur :  
  
||||  
|-|-|-|  
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|  
|[\<exception >](../ide/exception-visual-cpp.md)1|[\<Inclure >](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|  
|[\<para>](../ide/para-visual-cpp.md)|[\<param >](../ide/param-visual-cpp.md)1|[\<paramref >](../ide/paramref-visual-cpp.md)1|  
|[\<autorisation >](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|  
|[\<consultez >](../ide/see-visual-cpp.md)1|[\<seealso >](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|  
|[\<value>](../ide/value-visual-cpp.md)|||  
  
 1. Compilateur vérifie la syntaxe.  
  
 Dans la version actuelle, le compilateur Visual C++ ne prend pas en charge `<paramref>`, une balise qui est pris en charge par d’autres compilateurs Visual Studio. Visual C++ peut prendre en charge `<paramref>` dans une version ultérieure.  
  
## <a name="see-also"></a>Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)