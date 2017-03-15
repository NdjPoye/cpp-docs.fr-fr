---
title: "uuid (C++ Attributes) | Microsoft Docs"
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
  - "vc-attr.uuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uuid attribute"
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++ Attributes)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie l'identificateur unique d'une classe ou une interface.  
  
## Syntaxe  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### Paramètres  
 *uuid*  
 un 128 bits, identificateur unique.  
  
## Notes  
 Si la définition d'une interface ou classe ne spécifie pas l'attribut d' `uuid` C\+\+, le compilateur Visual C\+\+ fournit un.  Lorsque vous spécifiez `uuid`, vous devez inclure les guillemets.  
  
 Si vous ne spécifiez pas `uuid`, le compilateur génère même GUID pour les interfaces ou des classes avec le même nom dans des projets d'attribut sur un ordinateur.  
  
 Vous pouvez utiliser Uuidgen.exe ou Guidgen.exe pour générer vos propres identificateurs uniques.  \(Pour exécuter l'une ou l'autre de ces outils, cliquez sur **Démarrer** et cliquez sur **Exécuter** dans le menu.  Entrez le nom de l'outil requis.\)  
  
 Lorsqu'il est utilisé dans un projet qui n'utilise pas également ATL, spécifier l'attribut pour `uuid` est le même que spécifiant le modificateur de \_\_declspec d' [uuid](../cpp/uuid-cpp.md) .  Pour récupérer `uuid` d'une classe, vous pouvez utiliser [\_\_uuidof](../cpp/uuidof-operator.md)  
  
## Exemple  
 Consultez l'exemple de [pouvant être liée](../windows/bindable.md) pour un usage d'exemple d' `uuid`.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`, `interface`, **union**, `enum`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)