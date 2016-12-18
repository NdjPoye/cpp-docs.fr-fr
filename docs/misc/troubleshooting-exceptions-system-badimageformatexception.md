---
title: "D&#233;pannage des exceptions&#160;: System.BadImageFormatException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "BadImageFormatException (classe)"
ms.assetid: 8d2b385a-3d6d-4dfa-8546-7ece562867e3
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.BadImageFormatException
Une exception <xref:System.BadImageFormatException> est levée lorsque l'image fichier d'une DLL ou d'un programme exécutable n'est pas valide.  
  
## Conseils associés  
 **Si votre application utilise les composants 32 bits, assurez\-vous qu'elle s'exécute toujours comme une application 32 bits.**  
 Si la propriété **Plateforme cible** de votre projet d'application a la valeur `AnyCPU`, l'application compilée peut être exécutée en mode 64 bits ou 32 bits. Lorsqu'il s'exécute comme une application 64 bits, le compilateur juste\-à\-temps \(JIT\) génère du code natif 64 bits. Si l'application dépend d'un composant managé ou natif 32 bits, ce composant ne pourra pas être chargé en mode 64 bits. Pour résoudre ce problème, attribuez la valeur `x86` à la propriété **Plateforme cible**, puis recompilez.  
  
 **Vérifiez que vous n'utilisez pas un composant ayant été créé avec une autre version de .NET Framework.**  
 Cette exception est levée lorsqu'une application ou un composant développé à l'aide de [!INCLUDE[net_v10_short](../misc/includes/net_v10_short_md.md)] ou [!INCLUDE[net_v11_short](../misc/includes/net_v11_short_md.md)] tente de charger un assembly développé à l'aide de [!INCLUDE[net_v20SP1_short](../misc/includes/net_v20sp1_short_md.md)] ou version ultérieure, ou lorsqu'une application développée à l'aide de [!INCLUDE[net_v20SP1_short](../misc/includes/net_v20sp1_short_md.md)] ou [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)] tente de charger un assembly développé à l'aide de [!INCLUDE[net_v40_short](../misc/includes/net_v40_short_md.md)]. L'exception <xref:System.BadImageFormatException> peut être signalée comme une erreur de compilation ou être levée au moment de l'exécution. Pour obtenir un exemple, consultez la classe <xref:System.BadImageFormatException>.  
  
 **Assurez\-vous que l'image fichier est un assembly managé ou un module valide.**  
 Cette exception est levée lorsqu'une bibliothèque de liaisons dynamiques ou un fichier exécutable managé <xref:System.Reflection.Assembly.Load%2A> sont passés à la méthode en vue du chargement.  
  
 Pour plus d’informations, les utilisateurs de Visual Basic peuvent consulter la rubrique [Troubleshooting Interoperability](../Topic/Troubleshooting%20Interoperability%20\(Visual%20Basic\).md).  
  
## Remarques  
 La réflexion sur des fichiers exécutables C\+\+ peut lever cette exception. Cela provient généralement de la suppression des adresses de réadressage ou de la section .Reloc du fichier exécutable par le compilateur C\+\+. Pour conserver l'adresse de réadressage dans un fichier exécutable C\+\+, spécifiez **\/fixed:no** lors de la liaison.  
  
 Pour connaître les autres causes possibles de cette exception, consultez la classe <xref:System.BadImageFormatException>.  
  
## Voir aussi  
 <xref:System.BadImageFormatException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)