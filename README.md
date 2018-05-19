Role Name
=========

A role to configure deployed postgresql server. 

Requirements
------------

Runs on recent debian systems.  

Role Variables
--------------
       
    # Apt packages required by postgresql_* ansible modules
    postgres_init_apt_dependencies:
      - python-psycopg2
    
    # Login credentials to posgresql server. 
    postgres_init_host: localhost
    postgres_init_port: 5432
    postgres_init_login_root_user: postgres
    
    # You need to set that! 
    postgres_init_login_root_password: null
    
    # Postgresql users to configure
    postgres_init_users:
      # User with plaintext password 
      - name: dbusr1
        password: plaintext-password
      # Delete user
      - name: disabled-user
        state: absent
       # User with md5 password 
      - name: dbusr2
        password: md5d011966da94d776cf59bf6dbde240e5d
        
    postgres_init_databases:
        # Create the db 
        - name: db1
          owner: db1usr
        # Drop db  
        - name: disabled-db
          state: absent


Dependencies
------------

None


License
-------

BSD

Author Information
------------------

Jacek Bzdak <jacek@askesis.pl>
