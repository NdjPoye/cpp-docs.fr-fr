---
title: -/CLRUNMANAGEDCODECHECK (Ajouter SupressUnmanagedCodeSecurityAttribute) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /CLRUNMANAGEDCODECHECK
dev_langs: C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4810da2a1dd24893a1e69a35091b3a7c89b527e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (Ajouter SupressUnmanagedCodeSecurityAttribute)
**/CLRUNMANAGEDCODECHECK** Spécifie si l’éditeur de liens doit appliquer <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> généré à l’éditeur de liens `PInvoke` appelle du code managé dans des DLL natives.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## <a name="remarks"></a>Remarques  
 Par défaut, l’éditeur de liens applique SuppressUnmanagedCodeSecurityAttribute aux généré par l’éditeur de liens `PInvoke` appels. Lorsque **/CLRUNMANAGEDCODECHECK** est activée, SuppressUnmanagedCodeSecurityAttribute n’est pas appliqué.  
  
 L’éditeur de liens ajoute seulement l’attribut aux objets compilés avec **/CLR** ou **/CLR : pure**. L’éditeur de liens ne génère pas `PInvoke` appelle dans les objets compilés avec **/CLR : safe**. Pour plus d’informations, consultez l’article [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md). Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 A `PInvoke` appel est généré par l’éditeur de liens lors de l’éditeur de liens ne peut pas détecter de symbole managé pour répondre à une référence à partir d’un appelant managé, mais peut rechercher un symbole natif correspondant à cette référence. Pour plus d’informations sur `PInvoke`, consultez [appelant les fonctions natives à partir de Code managé](../../dotnet/calling-native-functions-from-managed-code.md).  
  
 Notez que si vous utilisez <xref:System.Security.AllowPartiallyTrustedCallersAttribute> dans votre code, vous devez définir explicitement **/CLRUNMANAGEDCODECHECK**. Il est une faille de sécurité potentielle si une image contient à la fois les attributs SuppressUnmanagedCodeSecurity et AllowPartiallyTrustedCallers.  
  
 Consultez [instructions de codage sécurisé pour le Code non managé](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) pour plus d’informations sur les conséquences de l’utilisation de SuppressUnmanagedCodeSecurityAttribute.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’éditeur de liens** nœud.  
  
4.  Sélectionnez le **avancé** page de propriétés.  
  
5.  Modifier la **vérification du Code non managé CLR** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)