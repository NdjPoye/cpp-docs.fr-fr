---
title: "import | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.import"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "import attribute"
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# import
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie .idl, un .odl, ou un fichier d'en\-tête différent contenant des définitions que vous souhaitez référencer de votre IDL principal.  
  
## Syntaxe  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### Paramètres  
 `idl_file`  
 Le nom d'un fichier .idl que vous souhaitez a importé dans la bibliothèque de types du projet actuel.  
  
## Notes  
 L'attribut d' **importation** C\+\+ provoque une instruction d' `#import` à placer sous l'instruction d' `import "docobj.idl"` dans le fichier généré .idl.  L'attribut d' **importation** a les mêmes fonctionnalités que l'attribut d' [importation](http://msdn.microsoft.com/library/windows/desktop/aa367047) MIDL.  
  
 L'attribut d' **importation** place uniquement le fichier spécifié dans le fichier .idl qui sera généré par votre projet ; l'attribut d' **importation** ne vous permet pas appeler des éléments dans le fichier spécifié de code source dans votre projet.  Pour appeler des éléments dans le fichier spécifié de code source dans votre projet, l'utilisation [\#import](../preprocessor/hash-import-directive-cpp.md) et l'attribut d' `embedded_idl` ou vous pouvez inclure le fichier .h pour `idl_file`, si un fichier .h existe.  
  
## Exemple  
 Le code suivant :  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 produit le code suivant dans le fichier généré .idl :  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|n'importe où|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)