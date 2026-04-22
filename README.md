while true
do
    echo ""
    echo "===== Time Zone Script ====="
    echo "1. Show current date and time"
    echo "2. Change time zone"
    echo "3. Show time with seconds & milliseconds"
    echo "4. World clock"
    echo "5. Detailed date info"
    echo "6. Exit"

    read -p "Enter your choice: " choice

    case $choice in
        1)
            echo "Current Date and Time:"
            date
            ;;
        2)
            echo "Available Time Zones:"
            timedatectl list-timezones | head -20
            read -p "Enter Time Zone: " tz
            sudo timedatectl set-timezone $tz
            ;;
        3)
            date "+%Y-%m-%d %H:%M:%S.%3N"
            ;;
        4)
            echo "India:"
            TZ="Asia/Kolkata" date
            ;;
        5)
            echo "Detailed Date Info:"
            date -R
            ;;
        6)
            echo "Exiting..."
            break
            ;;
        *)
            echo "Invalid choice"
            ;;
    esac
done
