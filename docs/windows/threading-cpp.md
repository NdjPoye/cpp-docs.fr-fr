---
title: "threading (C++) | Microsoft Docs"
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
  - "vc-attr.threading"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threading attribute"
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# threading (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie le modèle de thread pour un objet COM.  
  
## Syntaxe  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### Paramètres  
 ***modèle*** \(facultatif\)  
 L'un des modèles de thread suivants :  
  
-   **apartment \(cloisonné\)** \(thread cloisonné\)  
  
-   **Neutre** \(composants .NET Framework sans interface utilisateur\)  
  
-   **unique** \(threading simple\)  
  
-   **libre** \(modèle de thread libre\)  
  
-   **les deux** \(modèles de thread cloisonné \(STA\) et libre\)  
  
 la valeur par défaut est **apartment \(cloisonné\)**.  
  
## Notes  
 L'attribut de **threads** C\+\+ n'apparaît pas dans le fichier généré .idl mais sera utilisé dans l'implémentation de votre objet COM.  
  
 Dans les projets ATL, si l'attribut de [coclasse](../windows/coclass.md) est également présent, le modèle de thread spécifié par *le modèle* est passé comme paramètre de modèle à la classe de [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) , l'insertion par l'attribut de **coclasse** .  
  
 l'attribut de **threads** garde également l'accès à [event\_source](../windows/event-source.md).  
  
## Exemple  
 Consultez l'exemple d' [autorisé](../windows/licensed.md) pour un usage d'exemple de **threads**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|**coclasse**|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Prise en charge du multithreading pour le code plus ancien \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Neutral Apartments](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)