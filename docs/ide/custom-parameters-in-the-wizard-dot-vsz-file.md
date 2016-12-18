---
title: "Param&#232;tres personnalis&#233;s dans le fichier .Vsz de l&#39;Assistant | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABSOLUTE_PATH (macro)"
  - "Assistants personnalisés, .vsz (fichier)"
  - "HTML_FILTER (macro)"
  - "HTML_PATH (macro)"
  - "IMAGE_FILTER (macro)"
  - "IMAGES_PATH (macro)"
  - "MISC_FILTER (macro)"
  - "PRODUCT (macro)"
  - "PRODUCT_INSTALLATION_DIR (macro)"
  - "PROJECT_TEMPLATE_NAME (macro)"
  - "PROJECT_TEMPLATE_PATH (macro)"
  - "RELATIVE_PATH (macro)"
  - "SCRIPT_COMMON_PATH (macro)"
  - "SCRIPT_FILTER (macro)"
  - "SCRIPT_PATH (macro)"
  - "START_PATH (macro)"
  - "TEMPLATE_FILTER (macro)"
  - "TEMPLATES_PATH (macro)"
  - "WIZARD_NAME (macro)"
  - "WIZARD_UI (macro)"
ms.assetid: 560dd5c0-7cff-4974-b856-5ca25b0669b8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Param&#232;tres personnalis&#233;s dans le fichier .Vsz de l&#39;Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans ses deux premières lignes, le fichier .vsz identifie la version de l'Assistant et le ProgID ou CLSID de l'Assistant à co\-créer.  Le fichier .vsz peut aussi inclure des paramètres de contexte facultatifs ainsi que des paramètres personnalisés ajoutés à la table de symboles \(en plus des symboles fournis dans la section de symboles HTML\).  
  
 La méthode <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> affiche l'Assistant, qui prend un tableau du contexte et les paramètres personnalisés définis dans le fichier .vsz comme ses paramètres.  
  
 Les symboles ci\-dessous sont couramment utilisés et spécifiés comme paramètres personnalisés dans le [fichier .vsz](../ide/dot-vsz-file-project-control.md) ou les fichiers .htm, ils sont utilisables dans les fichiers HTML, scripts ou modèles de l'Assistant.  
  
## Exemple  
 Comme l'indiquent les entrées du fichier .vsz ci\-dessous, l'Assistant MyProjWiz contient une interface utilisateur.  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine  
Param="WIZARD_NAME = MyProjWiz"  
Param="WIZARD_UI = TRUE"  
```  
  
### Symboles de paramètres personnalisés dans le fichier .vsz de l'Assistant  
  
|Symbole|Définition|  
|-------------|----------------|  
|ABSOLUTE\_PATH|Emplacement des fichiers de l'Assistant.|  
|HTML\_FILTER|Spécifié dans le fichier .vsz.  Types de fichiers placés dans le dossier des fichiers HTML de l'**Explorateur de solutions**.  Le plus souvent « htm ».|  
|HTML\_PATH|Spécifié dans le fichier .vsz.  Emplacement des [fichiers HTML](../ide/html-files.md) de l'Assistant.  Par défaut, c'est START\_PATH\\HTML\\*LANGUAGE* \(où *LANGUAGE* est le paramètre régional spécifié par la base de registres\). **Note:**  Vous pouvez spécifier une langue différente en définissant \<LangID\> avec la valeur décimale de HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\7.0\\General\\UILanguage.  Pour plus d'informations, consultez [Localisation d'un Assistant dans plusieurs langues](../ide/localizing-a-wizard-to-multiple-languages.md).  Pour obtenir la liste des valeurs décimales de langue, consultez [Prise en charge d'autres langues par l'Assistant](../ide/wizard-support-for-other-languages.md).|  
|IMAGE\_FILTER|Spécifié dans le fichier .vsz.  Types de fichiers placés dans le dossier des fichiers images de l'Explorateur de solutions.  Le plus souvent « bmp;gif »|  
|IMAGES\_PATH|Spécifié dans le fichier .vsz.  Emplacement des fichiers images utilisés dans les fichiers html.  Par défaut, START\_PATH\\Images.|  
|MISC\_FILTER|Spécifié dans le fichier .vsz.  Types de fichiers placés dans le dossier Fichiers divers de l'Explorateur de solutions.  Le plus souvent « vsz;vsdir;ico;vcproj;csproj;css;inf ».|  
|PRODUCT|Par défaut, défini comme Visual C\+\+ ; peut aussi être défini comme Visual Basic pour créer des Assistants Visual Basic, et ainsi de suite.|  
|PRODUCT\_INSTALLATION\_DIR|Répertoire énuméré dans la liste de la base de registres HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\7.0\\Setup\\\<Product\>\\ ProductDir.|  
|PROJECT\_TEMPLATE\_NAME|Spécifié dans le fichier .vsz.  Fichier modèle du projet utilisé par votre Assistant pour créer des projets.  Le plus souvent « txt ».|  
|PROJECT\_TEMPLATE\_PATH|Répertoire qui contient les [fichiers modèles](../ide/template-files.md) du projet.  Pour Visual C\+\+, c'est par défaut PRODUCT\_INSTALLATION\_DIR\\VCWizards.|  
|RELATIVE\_PATH|Si ABSOLUTE\_PATH est introuvable, c'est RELATIVE\_PATH qui est essayé.  C'est le chemin d'accès relatif à PRODUCT\_INSTALLATION\_DIR.  Pour Visual C\+\+, RELATIVE\_PATH est PRODUCT\_INSTALLATION\_DIR\\VCWizards.|  
|SCRIPT\_COMMON\_PATH|Nom du répertoire par rapport à PRODUCT\_INSTALLATION\_DIR, qui contient le fichier de script commun.  Pour Visual C\+\+, c'est par exemple VCWizards.|  
|SCRIPT\_FILTER|Spécifié dans le fichier .vsz.  Types de fichiers placés dans le dossier des fichiers de script de l'Explorateur de solutions.  Le plus souvent « js » \(JScript\) ou « vbs » \(VBScript\).|  
|SCRIPT\_PATH|Emplacement du [fichier JScript](../ide/jscript-file.md) de l'Assistant.  Par défaut, c'est START\_PATH\\Scripts|  
|START\_PATH|Spécifié dans le fichier .vsz.  Non défini par l'utilisateur, mais utilisé en interne pour identifier RELATIVE\_PATH ou ABSOLUTE\_PATH.  Le nom de l'Assistant \(WIZARD\_NAME\) est ajouté à cette valeur.|  
|TEMPLATE\_FILTER|Spécifié dans le fichier .vsz.  Types de fichiers placés dans le dossier des fichiers modèles de l'Explorateur de solutions.  Le plus souvent « txt ».|  
|TEMPLATES\_PATH|Spécifié dans le fichier .vsz.  Emplacement des fichiers modèles de l'Assistant.  Par défaut, c'est START\_PATH\\Templates\\\<LangID\>. **Note:**  Consultez HTML\_PATH pour plus d'informations sur LangID.|  
|WIZARD\_NAME|Spécifie le nom de l'Assistant.  Situé dans le fichier .vsz, utilisé par le reste des symboles.|  
|WIZARD\_UI|Spécifié dans le fichier .vsz.  Valeur booléenne indiquant si l'Assistant contient une interface utilisateur.  Spécifiez **TRUE** pour une interface utilisateur ou **FALSE** en l'absence d'interface utilisateur.|  
  
## Voir aussi  
 <xref:EnvDTE.IDTWizard.Execute%2A>   
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)