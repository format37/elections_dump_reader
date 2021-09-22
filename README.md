# Load elections data from postgresql in to pandas dataframe
1. Download sql dump from https://observer.mos.ru/all/
2. unzip dump
```
gunzip observer-20210921_143000.sql.gz
```
3. move dump to data/ folder
```
mv observer-20210921_143000.sql data/
```
4. Pull postgres docker image
```
docker pull postgres
```
5. define src path
```
nano run_postgres.sh
```
and run postgresql container
```
sh run_postgres.sh
```
6. shell login into container (using portainer, for example)
7. inside container, connect to psql:
```
psql -U postgres
```
and create db and exit:
```
create database observer;
exit
```
8. load dump into observer db
```
psql -U postgres observer < observer-20210921_143000.sql
```
9. exit from container
```
exit
```
10. open jupyter notebook, define host ip, connect to psql and load data to pandas dataframe   

Data overview:   
https://github.com/kbespalov/voting2021/tree/6b47e213987f953a573e3d48c6159914da679e77
