---
title: '&lt;autorisation&gt; (Visual C++) | Documents Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- permission
- <permission>
dev_langs: C++
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 416467782be92760ac999301f9899be1260905aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ltpermissiongt-visual-c"></a>&lt;autorisation&gt; (Visual C++)
La balise \<permission> vous permet de documenter l’accès d’un membre. <xref:System.Security.PermissionSet>vous permet de spécifier l’accès à un membre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `member`  
 Référence à un membre ou un champ qu’il est possible d’appeler à partir de l’environnement de compilation actuel. Le compilateur vérifie que l’élément de code donné existe et traduit `member` en nom d’élément canonique dans le fichier XML de sortie.  Mettez le nom entre guillemets simples ou doubles.  
  
 Le compilateur émet un avertissement s'il ne trouve pas `member`.  
  
 Pour plus d’informations sur la création d’une référence cref à un type générique, consultez [\<see>](../ide/see-visual-cpp.md).  
  
 `description`  
 Description de l’accès au membre.  
  
## <a name="remarks"></a>Notes  
 Compilez avec [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour placer les commentaires de documentation dans un fichier en vue de les traiter.  
  
 Le compilateur Visual C++ tente de résoudre les références cref en une seule passe via les commentaires de la documentation.  Par conséquent, si lorsque vous utilisez les règles de recherche C++, un symbole est introuvable par le compilateur, la référence est marquée comme non résolue. Consultez [ \<seealso >](../ide/seealso-visual-cpp.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)