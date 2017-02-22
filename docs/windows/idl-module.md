---
title: "idl_module | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.idl_module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_module attribute"
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# idl_module
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie un point d'entrée dans un fichier.DLL.  
  
## Syntaxe  
  
```  
  
      [ idl_module (   
   name=module_name,   
   dllname=dll,   
   uuid="uuid",   
   helpstring="help text",   
   helpstringcontext=helpcontextID,   
   helpcontext=helpcontext,   
   hidden,   
   restricted  
) ]  
function declaration  
```  
  
#### Paramètres  
 **nom**  
 Un nom défini par l'utilisateur pour le bloc de code qui apparaîtra dans le fichier .idl.  
  
 **nomdll** \(facultatif\)  
 le fichier.DLL qui contient l'exportation.  
  
 `uuid` \(facultatif\)  
 ID unique.  
  
 **helpstring** \(facultatif\)  
 Une chaîne de caractères pour décrire la bibliothèque de types.  
  
 **helpstringcontext** \(facultatif\)  
 L'ID d'une rubrique d'aide dans un fichier de .hlp ou .chm.  
  
 **helpcontext** \(facultatif\)  
 L'ID d'aide pour cette bibliothèque de types.  
  
 **masqué** \(facultatif\)  
 Un paramètre qui empêché la bibliothèque à afficher.  Consultez l'attribut de [masqué](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL pour plus d'informations.  
  
 ***limité***  \(facultatif\)  
 Les membres de la bibliothèque ne peuvent pas être arbitrairement appelés.  Consultez l'attribut de [limité](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL pour plus d'informations.  
  
 *déclaration de fonction*  
 la fonction que vous définirez.  
  
## Notes  
 L'attribut d' `idl_module` C\+\+ vous permet de spécifier le point d'entrée dans un fichier .DLL, qui vous permet à l'importation en partir d'un fichier .DLL.  
  
 L'attribut d' **idl\_module** a des fonctionnalités semblables à l'attribut de [module](http://msdn.microsoft.com/library/windows/desktop/aa367099) MIDL.  
  
 Vous pouvez exporter une valeur d'un objet COM que vous pouvez exporter à partir d'un fichier .DLL en mettant un point d'entrée de DLL dans le bloc bibliothèque d'un fichier .idl.  
  
 Votre utilisation `idl_module` doit correspondre en deux étapes.  En premier lieu, vous devez définir une paire de name\/DLL.  Ensuite, lorsque vous utilisez `idl_module` pour spécifier un point d'entrée, spécifiez le nom et les attributs supplémentaires.  
  
## Exemple  
 Le code suivant montre comment utiliser l'attribut d' `idl_module` :  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
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
 [entry](../windows/entry.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)