---
title: '&lt;exception&gt; (Visual C++) | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- exception
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d3d5b7a89a3725ae9dee2065bcd21d8f114ca00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="ltexceptiongt-visual-c"></a>&lt;exception&gt; (Visual C++)
La balise \<exception> vous permet de spécifier quelles exceptions peuvent être levées. Cette balise est appliquée à une définition de méthode.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `member`  
 Référence à une exception qui est disponible à partir de l’environnement de compilation actuel. À l’aide des règles de recherche de nom, le compilateur vérifie que l’exception donnée existe et traduit `member` au nom d’élément canonique dans la sortie XML.  Le compilateur émet un avertissement s'il ne trouve pas `member`.  
  
 Mettez le nom entre guillemets simples ou doubles.  
  
 Pour plus d’informations sur la création d’une référence cref à un type générique, consultez [\<see>](../ide/see-visual-cpp.md).  
  
 `description`  
 Une description.  
  
## <a name="remarks"></a>Notes  
 Compilez avec [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour placer les commentaires de documentation dans un fichier en vue de les traiter.  
  
 Le compilateur Visual C++ tente de résoudre les références cref en une seule passe via les commentaires de la documentation.  Par conséquent, si lorsque vous utilisez les règles de recherche C++, un symbole est introuvable par le compilateur, la référence est marquée comme non résolue. Consultez [ \<seealso >](../ide/seealso-visual-cpp.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
  
```  
// xml_exception_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_exception_tag.dll  
using namespace System;  
  
/// Text for class EClass.  
public ref class EClass : public Exception {  
   // class definition ...  
};  
  
/// <exception cref="System.Exception">Thrown when... .</exception>  
public ref class TestClass {  
   void Test() {  
      try {  
      }  
      catch(EClass^) {  
      }  
   }  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)