---
title: "progid | Microsoft Docs"
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
  - "vc-attr.progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progid attribute"
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie l'identificateur programmatique pour un objet COM.  
  
## Syntaxe  
  
```  
  
      [ progid(  
   name  
) ];  
```  
  
#### Paramètres  
 *name*  
 l'identificateur programmatique représentant l'objet.  
  
 Présent de Progid une version explicite de l'identificateur de classe \(CLSID\) utilisé pour identifier des objets COM\/ActiveX.  
  
## Notes  
 L'attribut de **progid** C\+\+ vous permet de spécifier l'identificateur programmatique pour un objet COM.  Un progid a la forme *name1.name2.version*.  Si vous ne spécifiez pas *de version* d'un identificateur programmatique, la version par défaut est 1.  si vous ne spécifiez pas *name1.name2*, le nom par défaut est *classname.classname**.* Si vous ne spécifiez pas **progid** et vous spécifiez **vi\_progid**, *name1.name2*sont pris de **vi\_progid** et la version \(numéro séquentiel suivant\) est ajoutée.  
  
 Si un bloc d'attributs qui utilise **progid** n'utilise pas également `uuid`, le compilateur vérifiera le Registre pour voir si `uuid` existe pour **progid**spécifié.  Si **progid** n'est pas spécifié, la version \(et le nom de la coclasse, si vous créez une coclasse\) seront utilisés pour générer **progid**.  
  
 **progid** implique l'attribut de **coclasse** , c. autrement dit., si vous spécifiez **progid**, c'est la même que spécifiant les attributs de **coclasse** et de **progid** .  
  
 l'attribut de **progid** provoque une classe à enregistrer automatiquement sous le nom spécifié.  Le fichier généré .idl n'affiche pas la valeur de **progid** .  
  
 Lorsque cet attribut est utilisé dans un projet qui utilise ATL, le comportement de l'attribut change.  Outre le comportement ci\-dessus, les informations spécifiées avec cet attribut sont utilisées dans la fonction de **GetProgID** , injectée par l'attribut de **coclasse** .  Pour plus d'informations, consultez l'attribut de [coclasse](../windows/coclass.md) .  
  
## Exemple  
 Consultez l'exemple pour [coclasse](../windows/coclass.md) pour un usage d'exemple de **progid**.  
  
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
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)