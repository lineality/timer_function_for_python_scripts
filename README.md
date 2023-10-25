# timer_function_for_python_scripts


```python
import time
from datetime import datetime, timedelta

def start_timer():
    """
    requires:
        import time
        from datetime import datetime
    """
    # get time
    sample_time = datetime.utcnow()
    # make readable string
    readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')

    # Calculate time in different time zones
    readable_timestamp_est = (sample_time - timedelta(hours=5)).strftime('%Y-%m-%d %H:%M:%S')
    readable_timestamp_edt = (sample_time - timedelta(hours=4)).strftime('%Y-%m-%d %H:%M:%S')

    readable_timestamp_mst = (sample_time - timedelta(hours=7)).strftime('%Y-%m-%d %H:%M:%S')
    readable_timestamp_mdt = (sample_time - timedelta(hours=6)).strftime('%Y-%m-%d %H:%M:%S')

    readable_timestamp_pst = (sample_time - timedelta(hours=8)).strftime('%Y-%m-%d %H:%M:%S')
    readable_timestamp_pdt = (sample_time - timedelta(hours=9)).strftime('%Y-%m-%d %H:%M:%S')

    time_message = f"""
    Starting Time:
        UTC {readable_timesatamp}

        EST {readable_timestamp_est}
        EDT {readable_timestamp_edt}

        MST {readable_timestamp_mst}
        MDT {readable_timestamp_mdt}

        PST {readable_timestamp_pst}
        PDT {readable_timestamp_pdt}

    """
    print(time_message)

    start_stamp = time.time()
    return start_stamp


def end_timer(start_time):
    """
    requires: 
        import time
        start_time = time.time()
    """
    # get time
    sample_time = datetime.utcnow()
    # make readable string
    readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')

    # Calculate time in different time zones
    readable_timestamp_est = (sample_time - timedelta(hours=5)).strftime('%Y-%m-%d %H:%M:%S')
    readable_timestamp_edt = (sample_time - timedelta(hours=4)).strftime('%Y-%m-%d %H:%M:%S')

    readable_timestamp_mst = (sample_time - timedelta(hours=7)).strftime('%Y-%m-%d %H:%M:%S')
    readable_timestamp_mdt = (sample_time - timedelta(hours=6)).strftime('%Y-%m-%d %H:%M:%S')

    readable_timestamp_pst = (sample_time - timedelta(hours=8)).strftime('%Y-%m-%d %H:%M:%S')
    readable_timestamp_pdt = (sample_time - timedelta(hours=9)).strftime('%Y-%m-%d %H:%M:%S')

    time_message = f"""
    Finish Time:
        UTC {readable_timesatamp}

        EST {readable_timestamp_est}
        EDT {readable_timestamp_edt}

        MST {readable_timestamp_mst}
        MDT {readable_timestamp_mdt}

        PST {readable_timestamp_pst}
        PDT {readable_timestamp_pdt}
    """
    print(time_message)



    MARS_TO_EARTH = 1.02749125104

    # Record the end time
    end_time = time.time()
    # Calculate the elapsed time
    elapsed_time = end_time - start_time
    # Print the elapsed time in seconds


    count = elapsed_time
    total_mars_tenths = count * MARS_TO_EARTH
    total_mars_secs = total_mars_tenths // 10
    total_mars_mins = total_mars_secs // 60
    
    time_message = f"""
    Elapsed time: 
        posix epoch time: {elapsed_time} seconds
        Earth Time Total: {count//600} min {count%600/10:.1f} sec, Mars Time Total: {total_mars_mins:.0f} min {total_mars_secs%60 + total_mars_tenths%10 / 10:.1f} sec

    """
    print(time_message)



# Timer: For Start of Script
start_time = start_timer()

# ... Python script goes here...
time.sleep(2)  # This will pause the script for 5 seconds

# Timer: For End of Script
end_timer(start_time)
```
