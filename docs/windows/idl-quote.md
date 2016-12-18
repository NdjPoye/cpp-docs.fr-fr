---
title: "idl_quote | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.idl_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_quote attribute"
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# idl_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous permet d'utiliser les éléments IDL qui ne sont pas pris en charge dans la version actuelle de Visual C\+\+ et pour les faire passer le fichier généré .idl.  
  
## Syntaxe  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### Paramètres  
 *text*  
 Le nom de l'attribut que vous projetez le compilateur Visual C\+\+ pour passer au fichier généré .idl sans retourner une erreur du compilateur.  
  
## Notes  
 Si l'attribut d' **idl\_quote** C\+\+ est utilisé comme attribut autonome \(par un point\-virgule après le crochet fermant\), *le texte* est placé dans le fichier fusionné .idl comme.  si **idl\_quote** est utilisé sur un symbole, le *texte* est placé dans le bloc d'attributs pour ce symbole.  
  
## Exemple  
 Le code suivant illustre comment vous pouvez spécifier un attribut non pris en charge \(à l'aide de **dans**, qui est pris en charge\) et comment définir et utiliser un élément non défini .idl :  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 Ce code crée MYFLOT et MYDUB et *la saisie de texte* soient placées dans le fichier généré .idl.  Les avantages *de paramètre name* *texte* pour être placées avant que quelque chose qui fait référence au *nom* dans le fichier généré .idl.  Le paramètre *de dépendances* force les définitions de listes de dépendance à placer avant *texte* dans le fichier généré .idl.  
  
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
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)