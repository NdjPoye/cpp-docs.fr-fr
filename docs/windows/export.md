---
title: Exporter | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.export
dev_langs: C++
helpviewer_keywords: export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24619e3a0e707b40590b0ffb37b415629a18b1cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="export"></a>exporter
Provoque une structure de données doit être placé dans le fichier .idl.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
[export]  
  
```  
  
## <a name="remarks"></a>Notes  
 Le **exporter** attribut C++ provoque une structure de données doit être placé dans le fichier .idl et soit disponible dans la bibliothèque de types dans un format compatible binaire qui la rend disponible pour une utilisation avec n’importe quel langage.  
  
 Vous ne pouvez pas appliquer le **exporter** attribut à une classe, même si la classe possède uniquement des membres publics (l’équivalent d’un `struct`).  
  
 Si vous exportez sans nom `enum`s ou `struct`s, elles seront donné des noms qui commencent par **__unnamed***x*, où *x* est un numéro séquentiel.  
  
 Les typedefs valides pour l’exportation sont des types de base, les structures, unions, énumérations, ou tapez les identificateurs.  Consultez [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 Le code suivant montre comment utiliser le **exporter** attribut :  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**Union**, `typedef`, `enum`, `struct`, ou`interface`|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs du compilateur](../windows/compiler-attributes.md)   
 [Attributs Typedef, Enum, Union et Struct](../windows/typedef-enum-union-and-struct-attributes.md)   
