---
title: "/errorReport (Signaler les erreurs internes du compilateur) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ErrorReporting"
  - "/errorreport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/errorReport (option du compilateur C++)"
  - "-errorReport (option du compilateur C++)"
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# /errorReport (Signaler les erreurs internes du compilateur)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet de fournir les informations d'erreur interne du compilateur \(Internal Compiler Error ou ICE\) directement à Microsoft.  
  
## Syntaxe  
  
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## Arguments  
 **none**  
 Les rapports sur les erreurs internes du compilateur ne seront pas collectés ni envoyés à Microsoft.  
  
 **prompt**  
 Vous invite à envoyer un rapport dès qu'une erreur interne du compilateur se produit.  **prompt** est la valeur par défaut lorsqu'une application est compilée dans l'environnement de développement.  
  
 **queue**  
 Met en file d'attente le rapport d'erreurs.  Lorsque vous vous connectez avec des droits d'administrateur, une fenêtre indépendante s'affiche pour vous permettre de signaler toute défaillance depuis votre dernière connexion \(vous ne serez pas invité plus d'une fois tous les trois jours à envoyer des rapports pour les défaillances\).  **queue** est la valeur par défaut lorsqu'une application est compilée à une invite de commandes.  
  
 **send**  
 Envoie automatiquement les erreurs internes du compilateur à Microsoft.  Pour activer cette option, vous devez d'abord accepter la stratégie de collecte de données de Microsoft.  La première fois que vous spécifiez **\/errorReport:send** sur un ordinateur, un message du compilateur vous renvoie vers un site Web qui vous informe sur la stratégie de collecte de données de Microsoft.  
  
 Cette option dépend des paramètres du registre.  Pour plus d'informations sur la définition des valeurs appropriées dans le Registre, consultez [Comment activer un rapport d'erreur automatique dans les outils de ligne de commande Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695) sur le site Web MSDN.  
  
## Notes  
 Une erreur interne du compilateur \(Internal Compiler Error, ICE\) survient lorsque le compilateur ne peut pas traiter un fichier de code source.  Lorsqu'une telle erreur se produit, le compilateur ne génère pas de fichier de sortie ou de diagnostic utile permettant de corriger votre code.  
  
 Dans les versions antérieures, lorsque vous rencontriez une erreur interne du compilateur, vous étiez invité à contacter le Support technique Microsoft pour signaler le problème.  Avec **\/errorReport**, vous pouvez fournir directement des informations ICE à Microsoft.  Vos rapports d'erreurs peuvent permettre d'améliorer les futures versions du compilateur.  
  
 La capacité d'un utilisateur à envoyer des rapports dépend de l'ordinateur et des autorisations de la stratégie de l'utilisateur.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Rapport d'erreurs**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)