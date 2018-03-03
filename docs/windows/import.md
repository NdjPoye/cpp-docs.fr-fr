---
title: importer | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 011cabb37f388d4be6a9a69f685a7c711f0209a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="import"></a>d'importation
Spécifie un autre fichier .idl, .odl ou en-tête contenant des définitions à référencer à partir de votre fichier IDL principal.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Paramètres  
 `idl_file`  
 Le nom d’un fichier .idl que vous souhaitez importer dans la bibliothèque de types du projet actuel.  
  
## <a name="remarks"></a>Notes  
 Le **importer** C++ attribut entraîne une `#import` instruction doit être placé sous le `import "docobj.idl"` instruction dans le fichier .idl généré. Le **importer** attribut a les mêmes fonctionnalités que le [importer](http://msdn.microsoft.com/library/windows/desktop/aa367047) attribut MIDL.  
  
 Le **importer** attribut place uniquement le fichier spécifié dans le fichier .idl qui sera généré par votre projet ; le **importer** attribut ne permet pas d’appeler des constructions dans le fichier spécifié à partir de code source dans votre projet.  Pour appeler les constructions dans le fichier spécifié à partir de code source dans votre projet, soit utiliser [#import](../preprocessor/hash-import-directive-cpp.md) et `embedded_idl` attribut ou inclure le fichier .h pour la `idl_file`, s’il existe un fichier .h.  
  
## <a name="example"></a>Exemple  
 L'exemple de code suivant :  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 génère le code suivant dans le fichier .idl généré :  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
```  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|N'importe où|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs autonomes](../windows/stand-alone-attributes.md)   
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [inclure](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
