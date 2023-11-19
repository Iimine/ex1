# ex1
package Librairie;

public class Livre {
private String titre,auteur;
private int nbPages;
private static int nbLivres=0;
//Constructeur
public Livre() {
	titre = "";
    auteur = "";
    nbPages=0;
    nbLivres++;
}
public Livre(String unAuteur,String unTitre) {
	titre = unTitre;
	auteur = unAuteur;
	nbLivres++;
}
public Livre(String unAuteur,String unTitre,int unNbPages) {
	titre = unTitre;
    auteur = unAuteur;
    nbPages=unNbPages;
    nbLivres++;
}
public String getTitre() {
	return titre;
}

public void setTitre(String titre) {
	this.titre = titre;
}

public int getNbPages() {
	return nbPages;
}
public void setNbPages(int nbPages) {
	if(nbPages>0)
	this.nbPages = nbPages;
	else
		System.out.println("le nombre de pages doit etre positive");

}
public void setAuteur(String auteur) {
	this.auteur = auteur;
}

public String getAuteur() {
	return auteur;
}

public void afficher()

{
	//System.out.println("le livre : "+titre+" de "+auteur+" "+nbPages+" pages");
	System.out.println(toString());
}
public static int getNbLivres()
{
	return nbLivres;
	}
@Override
public String toString()
{
	return "le livre : "+titre+" de "+auteur+" "+nbPages+" pages";
}

@Override
public boolean equals(Object obj) {
	if (this == obj)
		return true;
	if (obj == null)
		return false;
	if (this.getClass() != obj.getClass())
		return false;

	Livre liv = (Livre) obj;

return auteur.equals(liv.auteur)& titre.equals(liv.titre)& nbPages==liv.nbPages;
}

///
import Librairie.Livre;

public class TestLivre {
public static void main(String[] args)
{
	int somme=0;

Livre livre1=new Livre("Bruce Eckel","Thinking in Java ");
Livre livre2=new Livre("Claude Delannoy","Programmer en Java");

Livre livre3=new Livre();
livre3.setTitre("Python pour les nuls");
livre3.setAuteur("John Paul Mueller");
livre3.setNbPages(100);
Livre livre4=new Livre("Robert C. Martin","Coder proprement");
livre4.setNbPages(290);
Livre livre5=new Livre("cClaude Delannoy","Programmer en langage C",340);
Livre livreI=new Livre("Claude Delannoy","Programmer en langage C",340);

System.out.println(livre1.getAuteur());
System.out.println(livre2.getAuteur());
livre1.setNbPages(70);
livre2.setNbPages(200);

System.out.println("le livre N°1: "+livre1.getTitre()+" de "+livre1.getAuteur()+" "+livre1.getNbPages()+" pages");
System.out.println("le livre N°2: "+livre2.getTitre()+" de "+livre2.getAuteur()+" "+livre2.getNbPages()+" pages");
somme=livre1.getNbPages()+livre2.getNbPages();
System.out.println("la somme de nombre de pages: "+somme);
livre1.afficher();
livre2.afficher();
System.out.println(livre1.toString());
System.out.println(livre5==livreI);

System.out.println(livre5.equals(livreI));

if (livre5.getAuteur().equals(livreI.getAuteur()))
	System.out.println("egaux");
else
	System.out.println("nom");	


if (livre5.equals(livreI))
	System.out.println("egaux");
else
	System.out.println("nom");	

System.out.println(Livre.getNbLivres());
Livre l10=new Livre();
System.out.println(Livre.getNbLivres());

}

}
}
