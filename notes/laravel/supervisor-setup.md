# Laravel Queue Supervisor

**Installation instructions:**

    sudo apt-get update
    
    sudo apt-get install supervisor

In `/etc/supervisor/conf.d/` create a `.conf` file. In this example, `laravel-worker.conf` (contents below). Give it execute permissions: `chmod +x laravel-worker.conf`.

Once the configuration file has been created, you may update the Supervisor configuration and start the processes using the following commands:

    sudo supervisorctl reread
    
    sudo supervisorctl update
    
    sudo supervisorctl start laravel-worker:*

You can see the `laravel-worker` process running with: `sudo supervisorctl`.

**Configuration:** `laravel-worker.conf`

    [program:laravel-worker]
    process_name=%(program_name)s_%(process_num)02d
    command=php /var/www/html/dev/laravel/artisan queue:work redis --sleep=3 --tries=3
    autostart=true
    autorestart=true
    user=root
    numprocs=10
    redirect_stderr=true
    stderr_logfile=/var/log/laravelworker.err.log
    stdout_logfile=/var/log/laravelworker.log

In this example, the `numprocs` directive will instruct Supervisor to run 10 `queue:work` processes and monitor all of them, automatically restarting them if they fail.
