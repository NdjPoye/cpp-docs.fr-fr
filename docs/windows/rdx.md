---
title: "rdx | Microsoft Docs"
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
  - "vc-attr.rdx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdx attribute"
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# rdx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

crée une clé de Registre ou modifie une clé de Registre existante.  
  
## Syntaxe  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### Paramètres  
 `key`  
 Le nom de la clé à créer ou à ouverte.  
  
 `valuename`\(facultatif\)  
 spécifie le champ de valeur à définir.  si un champ de valeur avec ce nom n'existe pas déjà dans la clé, il est ajouté.  
  
 *regtype*  
 Le type de clé de Registre ajoutée.  Peut avoir l'une des valeurs suivantes : **texte**, **DWORD**, **binaire**, ou `CString`.  
  
## Notes  
 L'attribut de **rdx** C\+\+ crée ou modifie une clé de Registre existante d'un composant COM.  l'attribut ajoute une macro de BEGIN\_RDX\_MAP à l'objet qui implémente le membre cible.  `RegistryDataExchange`, une fonction injectée par suite de la macro de BEGIN\_RDX\_MAP, peut servir à transférer des données entre le Registre et les données membres  
  
 Cet attribut peut être utilisé avec [coclasse](../windows/coclass.md), [progid](../windows/progid.md), les attributs ou de [vi\_progid](../windows/vi-progid.md) ou d'autres attributs qui implique une de ces derniers.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe** ou membre d' `struct`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Exemple  
 Le code suivant ajoute une clé de Registre appelée MyValue au système décrivant le composant COM de CMyClass.  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [registration\_script](../windows/registration-script.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)