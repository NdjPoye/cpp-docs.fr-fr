---
title: "cpp_quote | Microsoft Docs"
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
  - "vc-attr.cpp_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cpp_quote attribute"
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cpp_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Effectue la chaîne spécifiée, sans guillemets, dans le fichier généré .idl.  
  
## Syntaxe  
  
```  
  
      [ cpp_quote(  
   "statement"  
) ];  
```  
  
#### Paramètres  
 *statement*  
 Instruction c.  
  
## Notes  
 L'attribut de **cpp\_quote** C\+\+ est utile si vous souhaitez mettre une directive de préprocesseur dans un fichier .idl.  
  
 Vous pouvez également utiliser **cpp\_quote** et générer un fichier .h dans le cadre de la compilation de MIDL.  Par exemple, si vous avez le fichier d'en\-tête C\+\+ qui utilise des attributs C\+\+ IDL mais ne pouvez pas utiliser ce fichier pour une tâche, vous pouvez la compilation pour créer un fichier généré par le compilateur MIDL .h, que vous devez pouvoir utiliser.  
  
 L'attribut de **cpp\_quote** a les mêmes fonctionnalités que l'attribut de [cpp\_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [double](../windows/dual.md) pour un usage d'exemple comment utiliser **cpp\_quote**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|n'importe où|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)