[<img src="https://wiki.postgresql.org/images/a/a4/PostgreSQL_logo.3colors.svg" align="right" width="50">](https://www.postgresql.org/) 

## Postgres
 
## Definitions

* **Postmaster**: Manage all of the service behind the scene which are;
    * **Walwriter**: Write the transaction from WAL Buffer to WAL Segments.
    * **Background writer**, 
    * **Autovacuum**: Maintenance task for Indexes and Statistics.
    * **Sesions**: Database sessions. 
      * They can be see under the post master session. 
         * ps -ef 911
    * **Logger**: Log to all errors.
    * **Checkpointer**: Check every 5 min (by default) shared buffer and data files are sync.
    * **Stats collector**,
    * **Archiver**
    
* **WAL (Write ahead log)**: Write transaction to WAL Buffer area and then when transaction is commit data changes will be write on WAL Segments. 
    * Settings for WAL Buffer size.
    * **WAL Segment Size**: Transaction Log file size.
       
* **Database Cluster**: Instance

* **Default Databases**:
    * template0
    * template1
    * postgres

## Extentions
    
* **pg_lsclusters**: list clusters (instances) and some informations with it.
* **pg_ctl**: check status postgres service
    * /usr/lib/postgresql/14/bin/pg_ctl status -D /var/lib/postgresql/14/main
       * /usr/lib/postgresql/14/bin/pg_ctl -D /var/lib/postgresql/14/main -ms stop 
       * -ms(mart): smart mode which means postgres waiting for the every connection is closed.
       * -mf(ast): (default) fast mode which means every transaction will be rolled back and shut it down the server fastly.
       * -mi(mmediate): imediate mode which means connections are closed by service and without roll back. When the service is start, transactions will be roll back.

## :elephant: PSQL
   ```
   show config_file;        -- show pg_hba file location.
   show port;               -- show port information.
   show data_directory;     -- show data directory location.
   show hba_file;           -- show pg_hba file location.
   show config_file;        -- show config file location.
   select pg_reload_conf(); -- apply config to runtime configuration.
   ```
   
##### Server Configuration
  


