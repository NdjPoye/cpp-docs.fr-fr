---
title: "La biblioth&#232;que standard &#39;&lt;nom_fichier&gt;&#39; est introuvable | Microsoft Docs"
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
  - "vbc40049"
  - "bc40049"
helpviewer_keywords: 
  - "BC40049"
ms.assetid: a292f97e-4852-4021-b300-7ab47beb95d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La biblioth&#232;que standard &#39;&lt;nom_fichier&gt;&#39; est introuvable
[!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] n’a pas pu trouver ou ouvrir l’une des bibliothèques DLL standard nécessaires à la compilation et à la liaison.  
  
 La bibliothèque qui ne peut pas être utilisée est probablement mscorlib.dll ou microsoft.visualbasic.dll.  
  
 Par défaut, ce message est un avertissement. Pour plus d’informations sur le masquage des avertissements ou le traitement des avertissements en tant qu’erreurs, consultez [Configuration d'avertissements en Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **ID d’erreur :** BC40049  
  
### Pour corriger cette erreur  
  
1.  Vérifiez que le fichier mentionné dans le message d’erreur se trouve sur le disque dur à partir duquel vous exécutez [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]. Normalement, les bibliothèques standard doivent résider dans un sous\-répertoire sous \\WINNT\\Microsoft.NET\\Framework ou \\WINDOWS\\Microsoft.NET\\Framework.  
  
2.  Vérifiez que ni le fichier ni le répertoire ne possèdent un paramètre ou un attribut qui empêche [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] de bénéficier d’un accès en lecture.  
  
3.  Vérifiez que le nom de fichier et l’extension sont correctement orthographiés. L’utilisation de majuscules ne pose pas de problème.  
  
4.  Si le fichier est situé au bon endroit et est accessible, il est possible qu’il soit endommagé sur le disque. Si possible, réinstallez [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)].  
  
5.  Notez le nom exact du fichier et de l’extension, puis contactez les services de support technique Microsoft.  
  
## Voir aussi  
 [Génération à partir de la ligne de commande](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md)   
 [How to: Invoke the Command\-Line Compiler](../Topic/How%20to:%20Invoke%20the%20Command-Line%20Compiler%20\(Visual%20Basic\).md)   
 [Nous contacter](../Topic/Talk%20to%20Us.md)