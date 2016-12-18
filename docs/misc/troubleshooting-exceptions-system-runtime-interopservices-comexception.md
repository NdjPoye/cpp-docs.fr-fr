---
title: "D&#233;pannage des exceptions&#160;: System.Runtime.InteropServices.COMException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHCOM"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "COMException (classe)"
ms.assetid: 14b6de51-e039-4db7-9321-06c9e16e328a
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.Runtime.InteropServices.COMException
Une exception <xref:System.Runtime.InteropServices.COMException> est levée quand un HRESULT non reconnu est retourné d'un appel de méthode COM.  
  
## Conseils associés  
 **Vérifier la propriété ErrorCode de l'exception pour déterminer le HRESULT retourné par l'objet COM**  
 Lorsque le runtime rencontre un HRESULT inconnu, il lève une exception <xref:System.Runtime.InteropServices.COMException> qui inclut une propriété `ErrorCode` publique qui contient le HRESULT retourné par l'appel. Si un message d'erreur est disponible pour le runtime, le message est retourné à l'appelant. Si toutefois le développeur du composant COM a omis d'inclure un message d'erreur, le runtime retourne le HRESULT à huit chiffres à la place d'une chaîne de message. La présence d'un HRESULT permet à l'appelant de déterminer la cause de l'exception. Pour plus d'informations, consultez [How to: Map HRESULTs and Exceptions](../Topic/How%20to:%20Map%20HRESULTs%20and%20Exceptions.md).  
  
 **Désactivez le processus d'hébergement.**  
 COM permet la communication entre [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] et le processus d'hébergement. Comme il est utilisé avant l'exécution du code, un appel à `CoInitializeSecurity` entraîne la levée de cette exception.  
  
### Notes  
 Le Common Language Runtime transforme des HRESULT connus en exceptions .NET, ce qui permet à des objets COM de retourner des informations d'erreur pertinentes aux clients managés. Le mappage d'un HRESULT à une exception fonctionne également dans l'autre direction, en retournant des HRESULT spécifiques aux clients non managés.  
  
 Lorsque des paramètres à liaison tardive sont passés à des méthodes d'objets Microsoft Office, une exception <xref:System.Runtime.InteropServices.COMException> peut être levée lorsque les objets sont des objets COM. Le classeur tardif suppose que ces appels de méthode impliquent un paramètre `ByRef` et que la propriété que vous passez a un accesseur `Set`. Si la propriété n'a pas d'accesseur, le [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] génère une exception <xref:System.MissingMethodException> \(HRESULT CORE\_E\_MISSINGMETHOD\). Pour contourner ce problème, utilisez des objets à liaison anticipée ou passez une variable au lieu d'une propriété de l'objet.  
  
## Voir aussi  
 <xref:System.Runtime.InteropServices.COMException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Gestion des exceptions COM Interop](../Topic/Handling%20COM%20Interop%20Exceptions.md)