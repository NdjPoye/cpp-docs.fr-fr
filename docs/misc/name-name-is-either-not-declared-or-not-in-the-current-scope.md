---
title: "Le nom &#39;&lt;nom&gt;&#39; n’est pas d&#233;clar&#233; ou ne se trouve pas dans la port&#233;e actuelle | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36610"
  - "bc36610"
helpviewer_keywords: 
  - "BC36610"
ms.assetid: e66a4b8a-9252-42ae-a30d-341fad4f74be
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Le nom &#39;&lt;nom&gt;&#39; n’est pas d&#233;clar&#233; ou ne se trouve pas dans la port&#233;e actuelle
Une requête LINQ fait référence à un élément de programmation, mais le compilateur ne peut pas trouver d’élément ayant exactement ce nom.  
  
 **ID d’erreur :** BC36610  
  
### Pour corriger cette erreur  
  
1.  Vérifiez l’orthographe du nom dans l’instruction de référence.[!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] respecte la casse, mais toute autre variation dans l’orthographe constitue un nom différent. Notez que le caractère de soulignement \(`_`\) fait partie du nom et donc de l’orthographe.  
  
2.  Vérifiez que l’élément de programmation se trouve bien dans la portée. Si l’instruction de référence est en dehors de la région déclarant l’élément de programmation, vous devrez peut\-être qualifier le nom de l’élément. Pour plus d'informations, consultez [Scope in Visual Basic](../Topic/Scope%20in%20Visual%20Basic.md).  
  
3.  Vérifiez que l’opérateur d’accès aux membres \(`.`\) figure bien entre un objet et son membre. Par exemple, si vous disposez d’un contrôle <xref:System.Windows.Forms.TextBox> dont le nom est `TextBox1`, pour accéder à sa propriété <xref:System.Windows.Forms.TextBoxBase.Text%2A>, vous devez taper `TextBox1.Text`. Si, au lieu de cela, vous tapez `TextBox1Text`, vous créez un nom différent.  
  
## Voir aussi  
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [Visual Basic Naming Conventions](../Topic/Visual%20Basic%20Naming%20Conventions.md)   
 [References to Declared Elements](../Topic/References%20to%20Declared%20Elements%20\(Visual%20Basic\).md)