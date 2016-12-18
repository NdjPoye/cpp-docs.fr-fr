---
title: "D&#233;pannage des exceptions&#160;: System.NotSupportedException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
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
  - "NotSupportedException (classe)"
ms.assetid: a214e851-ee0f-4bbd-9f72-8769046526f3
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.NotSupportedException
Une exception <xref:System.NotSupportedException> est levée lorsqu'une méthode appelée n'est pas prise en charge ou lors d'une tentative de lecture, recherche ou écriture dans un flux qui ne prend pas en charge la fonctionnalité appelée.  
  
## Conseils associés  
 **Assurez\-vous que la méthode est prise en charge.**  
 Il y a des méthodes qui ne sont pas prises en charge dans la classe de base et dont il est attendu qu'elles soient plutôt implémentées dans les classes dérivées. Si une classe dérivée implémente uniquement un sous\-ensemble des méthodes de sa classe de base, elle lève une exception <xref:System.NotSupportedException> pour les méthodes non prises en charge.  
  
## Notes  
 Lorsque vous utilisez [!INCLUDE[Compact](../misc/includes/compact_md.md)] et P\/Invoke sur une fonction native, cette exception peut être levée dans les cas suivants :  
  
-   la déclaration dans le code managé est incorrecte ;  
  
-   [!INCLUDE[Compact](../misc/includes/compact_md.md)] ne prend pas en charge l'opération que vous tentez d'effectuer ;  
  
-   les noms de DLL sont tronqués lors de l'exportation.  
  
-   Dans ce cas :  
  
-   Recherchez toutes violations des restrictions P\/Invoke de [!INCLUDE[Compact](../misc/includes/compact_md.md)].  
  
-   Recherchez tous les arguments qui requièrent de la mémoire pré\-allouée. Si vous en trouvez, vous devez passer une référence à une variable existante.  
  
-   Vérifiez que les noms des fonctions exportées sont corrects. Cette vérification peut être réalisée à l'aide de DumpBin.exe.  
  
-   Vérifiez que vous n'essayez pas de passer un trop grand nombre d'arguments.  
  
## Voir aussi  
 <xref:System.NotSupportedException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)