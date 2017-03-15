---
title: "/vmm, /vms, /vmv (Repr&#233;sentation &#224; but g&#233;n&#233;ral) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vms"
  - "/vmm"
  - "/vmv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmm (option du compilateur C++)"
  - "/vms (option du compilateur C++)"
  - "/vmv (option du compilateur C++)"
  - "représentation à but général (options du compilateur)"
  - "héritage unique (option du compilateur)"
  - "héritage virtuel (option du compilateur)"
  - "vmm (option du compilateur C++)"
  - "-vmm (option du compilateur C++)"
  - "vms (option du compilateur C++)"
  - "-vms (option du compilateur C++)"
  - "vmv (option du compilateur C++)"
  - "-vmv (option du compilateur C++)"
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /vmm, /vms, /vmv (Repr&#233;sentation &#224; but g&#233;n&#233;ral)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisée lorsque [\/vmb, \/vmg \(Méthode de représentation\)](../../build/reference/vmb-vmg-representation-method.md) est sélectionné en tant que [méthode de représentation](../../build/reference/vmb-vmg-representation-method.md).  Ces options indiquent le modèle d'héritage de la définition de classe qui n'a pas encore été rencontrée.  
  
## Syntaxe  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## Notes  
 Les options sont décrites dans le tableau suivant.  
  
|Option|Description|  
|------------|-----------------|  
|**\/vmm**|Spécifie la représentation la plus générale d'un pointeur vers un membre d'une classe comme devant être une représentation qui utilise l'héritage multiple.<br /><br /> Le [mot clé d'héritage](../../cpp/inheritance-keywords.md) et l'argument correspondant à [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md) est **multiple\_inheritance**.<br /><br /> Cette représentation est plus large que celle qui est requise pour un héritage simple.<br /><br /> Si le modèle d'héritage d'une définition de classe pour laquelle est déclaré un pointeur vers un membre est de type virtuel, le compilateur génère une erreur.|  
|**\/vms**|Spécifie la représentation la plus générale d'un pointeur vers un membre d'une classe comme devant être une représentation qui soit n'utilise pas d'héritage, soit utilise un héritage simple.<br /><br /> Le [mot clé d'héritage](../../cpp/inheritance-keywords.md) et l'argument correspondant à [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md) est **single\_inheritance**.<br /><br /> C'est la plus petite représentation possible d'un pointeur vers un membre d'une classe.<br /><br /> Si le modèle d'héritage d'une définition de classe pour laquelle est déclaré un pointeur vers un membre est de type multiple ou virtuel, le compilateur génère une erreur.|  
|**\/vmv**|Spécifie la représentation la plus générale d'un pointeur vers un membre d'une classe comme devant être une représentation qui utilise l'héritage virtuel.  Elle ne génère jamais d'erreur et constitue l'option par défaut.<br /><br /> Le [mot clé d'héritage](../../cpp/inheritance-keywords.md) et l'argument correspondant à [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md) est **virtual\_inheritance**.<br /><br /> Par rapport aux deux autres options, cette option requiert un pointeur plus large et du code supplémentaire pour interpréter le pointeur.|  
  
 Lorsque vous spécifiez l'une de ces options de modèle d'héritage, le modèle en question est utilisé pour tous les pointeurs vers des membres de classe, indépendamment de leur type d'héritage ou du fait que le pointeur soit déclaré avant ou après la classe.  Par conséquent, si vous utilisez toujours des classes d'héritage simple, vous pouvez réduire la taille du code en compilant avec l'option **\/vms** ; cependant, si vous voulez utiliser le cas le plus général \(au détriment de la représentation de données la plus générale\), compilez avec l'option  **\/vmv**.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/vmb, \/vmg \(Méthode de représentation\)](../../build/reference/vmb-vmg-representation-method.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)