## Correction des requêtes

> abandon de la dernière requête trop tordue ...

### Trouver le nombre de sites de compétitions situés à plus de 5 km de la tour Eiffel.

/*
SELECT count(*)
FROM site_compet
WHERE ST_Distance(
	geom::geography,
	ST_SetSRID(ST_Makepoint(2.294438,48.858265),4326)::geography
)>5000;
*/

### Créer une vue matérialisée qui permet de connaître la distance en km de chaque site à Null Island.

/*
CREATE MATERIALIZED VIEW vm_distance_site_null_island AS
SELECT DISTINCT nom_site as site,
round(ST_Distance(sc.geom::geography,ST_GeometryFromText('POINT(0 0)',4326)::geography)::numeric/1000,2) as "Distance en km de Null Island"
FROM public.site_compet as sc
order by 1
*/

### Créer une vue des communes qui accueillent un site de compétition et compter le nombre de site par commune classé dans l'ordre décroissant.

/*
create view v_nb_site_commune as
SELECT distinct t1.id,t1.nom, count(t2.id) as "Nb de site",t1.geom
FROM public.commune as t1 JOIN public.site_compet as t2 ON st_contains(t1.geom,t2.geom)
group  by 1
order by "Nb de site" DESC;
*/

