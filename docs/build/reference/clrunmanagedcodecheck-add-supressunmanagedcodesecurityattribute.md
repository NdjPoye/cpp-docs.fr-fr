---
title: "/CLRUNMANAGEDCODECHECK (Ajouter SupressUnmanagedCodeSecurityAttribute) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRUNMANAGEDCODECHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRUNMANAGEDCODECHECK (option de l'éditeur de liens)"
  - "-CLRUNMANAGEDCODECHECK (option de l'éditeur de liens)"
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# /CLRUNMANAGEDCODECHECK (Ajouter SupressUnmanagedCodeSecurityAttribute)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/CLRUNMANAGEDCODECHECK** spécifie si l'éditeur de liens doit appliquer <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> aux appels `PInvoke` générés par l'éditeur de liens à partir du code managé dans des DLL natives.  
  
## Syntaxe  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## Notes  
 Par défaut, l'éditeur de liens applique SuppressUnmanagedCodeSecurityAttribute aux appels `PInvoke` générés par l'éditeur de liens.  Lorsque **\/CLRUNMANAGEDCODECHECK** est activé, SuppressUnmanagedCodeSecurityAttribute n'est pas appliqué.  
  
 L'éditeur de liens ajoute seulement l'attribut aux objets compilés avec **\/clr** ou **\/clr:pure**.  L'éditeur de liens ne génère pas d'appels `PInvoke` dans les objets compilés avec **\/clr:safe**.  Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Un appel `PInvoke` est généré par l'éditeur de liens lorsque ce dernier ne peut pas détecter de symbole managé pour répondre à une référence provenant d'un appelant managé, mais peut détecter un symbole natif correspondant à cette référence.  Pour plus d'informations sur `PInvoke`, consultez [Appel à des fonctions natives à partir de code managé](../../dotnet/calling-native-functions-from-managed-code.md).  
  
 Notez que si vous utilisez <xref:System.Security.AllowPartiallyTrustedCallersAttribute> dans votre code, vous devez définir **\/CLRUNMANAGEDCODECHECK** explicitement.  Il s'agit d'une faille de sécurité potentielle si une image contient à la fois les attributs SuppressUnmanagedCodeSecurity et AllowPartiallyTrustedCallers.  
  
 Pour plus d'informations sur les conséquences de l'utilisation de SuppressUnmanagedCodeSecurityAttribute, consultez [Security Optimizations](http://msdn.microsoft.com/fr-fr/cf255069-d85d-4de3-914a-e4625215a7c0).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Avancé**.  
  
5.  Modifiez la propriété **Vérification du code non managé CLR**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)