---
title: '&lt;consultez&gt; (Visual C++) | Documents Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <see>
- see
dev_langs:
- C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15e1aedefe6d20c181ff208f76a61f49e15f5214
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ltseegt-visual-c"></a>&lt;consultez&gt; (Visual C++)
La balise \<see> vous permet de spécifier un lien à partir de l’intérieur du texte. Utilisez [ \<seealso >](../ide/seealso-visual-cpp.md) pour indiquer le texte que vous souhaitez s’affichent dans la section Voir aussi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `member`  
 Référence à un membre ou un champ qu’il est possible d’appeler à partir de l’environnement de compilation actuel.  Mettez le nom entre guillemets simples ou doubles.  
  
 Le compilateur vérifie que l’élément de code donné existe et qu’il résout `member` nom de l’élément dans la sortie XML.  Le compilateur émet un avertissement s'il ne trouve pas `member`.  
  
## <a name="remarks"></a>Notes  
 Compilez avec [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) pour placer les commentaires de documentation dans un fichier en vue de les traiter.  
  
 Consultez [ \<Résumé >](../ide/summary-visual-cpp.md) pour obtenir un exemple d’utilisation de \<consultez >.  
  
 Le compilateur Visual C++ tente de résoudre les références cref en une seule passe via les commentaires de la documentation.  Par conséquent, si lorsque vous utilisez les règles de recherche C++, un symbole est introuvable par le compilateur, la référence est marquée comme non résolue. Consultez [ \<seealso >](../ide/seealso-visual-cpp.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment faire référence cref à un type générique, tel que le compilateur résout la référence.  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)