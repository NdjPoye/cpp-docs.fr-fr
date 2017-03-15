---
title: "vi_progid | Microsoft Docs"
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
  - "vc-attr.vi_progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vi_progid attribute"
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vi_progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie un formulaire indépendant de la version de l'identificateur programmatique.  
  
## Syntaxe  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### Paramètres  
 *name*  
 l'identificateur programmatique indépendant de la version représentant l'objet.  
  
 Présent de Progid une version explicite de l'identificateur de classe \(CLSID\) utilisé pour identifier des objets COM\/ActiveX.  
  
## Notes  
 L'attribut de **vi\_progid** C\+\+ vous permet de spécifier un progid indépendant de la version pour un objet COM.  Un progid a la forme *name1.name2.version*.  Un progid indépendant de la version n'a pas *de version*.  il est possible de spécifier **progid** et les attributs de **vi\_progid** sur une coclasse.  si vous ne spécifiez pas **vi\_progid**, l'identificateur programmatique indépendant de la version est la valeur spécifiée par l'attribut de [progid](../windows/progid.md) .  
  
 **vi\_progid** implique l'attribut de **coclasse** , c. autrement dit., si vous spécifiez **vi\_progid**, c'est la même que spécifiant les attributs de **coclasse** et de **vi\_progid** .  
  
 l'attribut de **vi\_progid** provoque une classe à enregistrer automatiquement sous le nom spécifié.  Le fichier généré .idl n'affiche pas la valeur d'identificateur programmatique.  
  
 dans les projets ATL, si l'attribut de [coclasse](../windows/coclass.md) est également présent, l'identificateur programmatique spécifié est utilisé par la fonction de **GetVersionIndependentProgID** \(insérée par l'attribut de **coclasse** \).  
  
## Exemple  
 Consultez l'exemple de [coclasse](../windows/coclass.md) pour un usage d'exemple de **vi\_progid**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)