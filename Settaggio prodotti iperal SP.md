*title

Vanno aggiunti i campi CARF_CANALE_LOCALE e CARF_CANALE_SECONDARIO VARCHAR(255)



/*operazione necessarie per test. Tutti i prodotti sono collegati al livello 4 dell'albero*/

select * from PRODOTTO as P inner join CATEGORIA as C on C.ID_CATEGORIA=P.ID_CATEGORIA where C.livello=4

select * from CATEGORIA  where livello=1 order by nome

select * from CATEGORIA  where livello=2 order by nome

/*acque*/
select * from CATEGORIA where livello=3 and id_padre=10128

select * from REPARTO_LOCALE

/*setto i grocery*/
update CATEGORIA set ID_REPARTO_LOCALE=1 where cod_int  in ('1_7','1_5','1_4','1_3','1_6')
/*propago i grocery*/
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=1 where  c2.cod_int  in ('1_7','1_5','1_4','1_3','1_6') 
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=1 where  c2.ID_REPARTO_LOCALE=1 and c.livello=3 and c2.livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=1 where  c2.ID_REPARTO_LOCALE=1 and c.livello=4 and c2.livello=3

/*setto le acque*/
update CATEGORIA set ID_REPARTO_LOCALE=21 where livello=3 and id_padre=10128 and cod_int='3_432' 
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=21 where  c2.ID_REPARTO_LOCALE=21 and c.livello=4 and c2.livello=3 

/*gastronomia 10 */
UPDATE CATEGORIA set ID_REPARTO_LOCALE=10 WHERE cod_int in ('2_25','2_12','2_13','2_24') and livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=10 where  c2.ID_REPARTO_LOCALE=10 and c.livello=3 and c2.livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=10 where  c2.ID_REPARTO_LOCALE=10 and c.livello=4 and c2.livello=3  

/*macelleria 15 2_14 2_23 2_15 */
UPDATE CATEGORIA set ID_REPARTO_LOCALE=15 WHERE cod_int in ('2_14','2_23','2_15') and livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=15 where  c2.ID_REPARTO_LOCALE=15 and c.livello=3 and c2.livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=15 where  c2.ID_REPARTO_LOCALE=15 and c.livello=4 and c2.livello=3 

/*pescheria 20 2_16*/
UPDATE CATEGORIA set ID_REPARTO_LOCALE=20 WHERE cod_int in ('2_16') and livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=20 where  c2.ID_REPARTO_LOCALE=20 and c.livello=3 and c2.livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=20 where  c2.ID_REPARTO_LOCALE=20 and c.livello=4 and c2.livello=3 

/*fresch 7*/
UPDATE CATEGORIA set ID_REPARTO_LOCALE=7 WHERE cod_int in ('2_22','2_11') and livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=7 where  c2.ID_REPARTO_LOCALE=7 and c.livello=3 and c2.livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=7 where  c2.ID_REPARTO_LOCALE=7 and c.livello=4 and c2.livello=3

/*surgelati 2_20 5*/
UPDATE CATEGORIA set ID_REPARTO_LOCALE=5 WHERE cod_int in ('2_20') and livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=5 where  c2.ID_REPARTO_LOCALE=5 and c.livello=3 and c2.livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=5 where  c2.ID_REPARTO_LOCALE=5 and c.livello=4 and c2.livello=3


/*pane 22 2_18,2_19 */
UPDATE CATEGORIA set ID_REPARTO_LOCALE=22 WHERE cod_int in ('2_18','2_19') and livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=22 where  c2.ID_REPARTO_LOCALE=22 and c.livello=3 and c2.livello=2
update CATEGORIA as c inner join CATEGORIA as c2 on c.id_padre=c2.id_categoria set c.ID_REPARTO_LOCALE=22 where  c2.ID_REPARTO_LOCALE=22 and c.livello=4 and c2.livello=3

 

update PRODOTTO as p inner join CATEGORIA  as c on c.id_categoria=p.id_categoria set p.id_reparto_locale=c.id_reparto_locale

select * from PRODOTTO