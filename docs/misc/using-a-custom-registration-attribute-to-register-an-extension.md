---
title: "Utilisation d’un attribut d’inscription personnalis&#233; pour inscrire une extension | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98068fa7-bda1-4922-b3f6-28680de58c3d
caps.latest.revision: 3
caps.handback.revision: 3
manager: "douge"
---
# Utilisation d’un attribut d’inscription personnalis&#233; pour inscrire une extension
Dans certains cas vous devrez peut\-être créer un attribut de nouvelle inscription de votre extension.  Vous pouvez utiliser des attributs d'alignement pour ajouter de nouvelles clés de Registre ou ajouter de nouvelles valeurs à exister des clés.  Le nouvel attribut doit dériver de <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, et il doit substituer l' <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> et les méthodes d' <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> .  
  
## Création d'un attribut personnalisé  
 Le code suivant montre comment créer un attribut de nouvelle inscription.  
  
```  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
    public class CustomRegistrationAttribute : RegistrationAttribute  
    {  
    }  
  
```  
  
 <xref:System.AttributeUsageAttribute> est utilisé sur les classes d'attributs pour spécifier l'élément de programme \(classe, méthode, etc.\) lequel l'attribut appartient, s'il peut être utilisé plusieurs fois, et s'il peut être héritée.  
  
### créer une clé de Registre  
 Dans le code suivant, l'attribut personnalisé crée une sous\-clé personnalisée sous la clé pour le VSPackage qui est stocké.  
  
```  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
  
```  
  
### Créer une nouvelle valeur dans une clé de Registre existante  
 Vous pouvez ajouter des valeurs personnalisées à une clé existante.  Le code suivant montre comment ajouter une nouvelle valeur dans une clé d'alignement d'un VSPackage.  
  
```  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
  
```