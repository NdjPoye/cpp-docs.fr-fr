---
title: "emitidl | Microsoft Docs"
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
  - "vc-attr.emitidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "emitidl attribute"
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# emitidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détermine si tous les attributs suivants IDL seront traités et placés dans le fichier généré .idl.  
  
## Syntaxe  
  
```  
  
      [ emitidl([boolean],  
   defaultimports=[boolean]  
) ] ;  
```  
  
#### Paramètres  
 `boolean`  
 valeurs possibles : **true**, **false**, **liaison**, **limité**, **push**, ou **bruit**.  
  
-   Si **true**, les attributs de catégorie IDL produits dans un fichier de code source sera placé dans le fichier généré .idl.  Il s'agit du paramètre par défaut pour **emitidl**.  
  
-   Si **false**, aucun attribut de catégorie IDL produit dans un fichier de code source ne sera pas placé dans le fichier généré .idl.  
  
-   Si **limité**, permet aux attributs IDL soit dans le fichier sans attribut de [module](../windows/module-cpp.md) .  Le compilateur ne génère pas de fichier .idl.  
  
-   Si **liaison**, substitue un attribut suivant de **limité** , qui requiert un fichier pour avoir un attribut de **module** s'il existe des attributs IDL dans le fichier.  
  
-   **push** vous permet d'enregistrer les paramètres actuels d' **emitidl** à une pile interne d' **emitidl** , et **bruit** vous permet de **emitidl** la valeur d'une valeur se trouve en haut de la pile interne d' **emitidl** .  
  
 **defaultimports** *\=*\[ `boolean`\] \(facultatif\)  
 -   Si `boolean` est **true**, docobj.idl sera importé dans le fichier généré .idl.  En outre, si un fichier .idl avec le même nom qu'un fichier .h que vous `#include` dans votre code source se trouve dans le même répertoire que le fichier .h, le fichier généré .idl contiendra une instruction Import pour ce fichier .idl.  
  
-   Si `boolean` est **false**, docobj.idl ne sera pas importé dans le fichier généré .idl.  Vous devrez importer explicitement des fichiers .idl à [importation](../windows/import.md).  
  
## Notes  
 Une fois l'attribut d' **emitidl** C\+\+ est produit dans un fichier de code source, les attributs de catégorie IDL seront placés dans le fichier généré .idl.  S'il n'y a aucun attribut d' **emitidl** , les attributs IDL dans le fichier de code source seront sortie au fichier généré .idl.  
  
 Il est possible que plusieurs attributs d' **emitidl** dans un fichier de code source.  Si `[emitidl(false)];` est produit dans un fichier sans `[emitidl(true)];`suivant, aucun attribut ne sera traité dans le fichier généré .idl.  
  
 chaque fois que le compilateur rencontre un nouveau fichier, **emitidl** est implicitement défini à **true**.  
  
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
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)