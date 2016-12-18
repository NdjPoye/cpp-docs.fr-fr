---
title: "no_injected_text | Microsoft Docs"
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
  - "vc-attr.no_injected_text"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_injected_text attribute"
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# no_injected_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur ne pourra pas d'injecter du code résultant de l'utilisation d'attributs.  
  
## Syntaxe  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### Paramètres  
 `boolean`\(facultatif\)  
 **true** si vous ne souhaitez pas de code injecté, **false** pour que le code à insérer.  **true** est la valeur par défaut.  
  
## Notes  
 L'utilisation la plus courante de l'attribut de **no\_injected\_text** C\+\+ est par l'option du compilateur de [\/Fx](../build/reference/fx-merge-injected-code.md) , ce qui insère l'attribut de **no\_injected\_text** dans le fichier de .mrg.  
  
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
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)