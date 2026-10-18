<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Verification - DAV College</title>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif;
            background-color: #e6e6e6;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
        }

        .container {
            background-color: #ffffff;
            width: 780px;
            padding: 40px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
            box-sizing: border-box;
            border: 1px solid #ccc;
        }

        /* Header Layout */
        .header-wrapper {
            position: relative;
            text-align: center;
            margin-bottom: 15px;
        }

        .logo-box {
            position: absolute;
            left: 0;
            top: 0;
            font-size: 13px;
            font-weight: bold;
            color: #333;
            line-height: 1.2;
        }

        .title-main {
            color: #e60000;
            font-size: 24px;
            margin: 0;
            font-weight: bold;
            letter-spacing: 0.5px;
        }

        .title-session {
            color: #b30000;
            font-size: 18px;
            margin: 5px 0 0 0;
            font-weight: bold;
        }

        .sub-header {
            text-align: center;
            font-size: 13px;
            font-weight: bold;
            color: #002244;
            margin-top: 20px;
            margin-bottom: 15px;
        }

        .divider {
            border: 0;
            height: 1.5px;
            background-color: #002244;
            margin-bottom: 25px;
        }

        /* Main Content Layout */
        .content {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
        }

        .details-table {
            width: 72%;
            border-collapse: collapse;
        }

        .details-table td {
            padding: 7px 0;
            font-size: 14px;
            vertical-align: top;
        }

        .details-table td.label {
            font-weight: bold;
            color: #111;
            width: 42%;
        }

        .details-table td.value {
            color: #333;
            width: 58%;
        }

        /* Photo and Signature Section */
        .media-box {
            width: 25%;
            display: flex;
            flex-direction: column;
            gap: 15px;
            align-items: flex-end;
        }

        .photo-box {
            width: 140px;
            height: 175px;
            border: 1px solid #444;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #fff;
            font-size: 15px;
            font-weight: bold;
            color: #222;
            text-align: center;
            overflow: hidden;
        }

        .photo-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .signature-box {
            width: 140px;
            height: 50px;
            border: 1px solid #444;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #fff;
            font-size: 15px;
            font-weight: bold;
            color: #222;
            overflow: hidden;
        }

        .signature-box img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }

        /* Footer Verified Status */
        .verified-text {
            text-align: center;
            color: #b30000;
            font-size: 26px;
            font-weight: bold;
            margin-top: 35px;
            margin-bottom: 15px;
            letter-spacing: 1px;
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Header Section -->
        <div class="header-wrapper">
            <div class="logo-box">
                DAVCS<br>Logo
            </div>
            <h1 class="title-main">DAV COLLEGE, SECTOR 10, CHANDIGARH</h1>
            <h2 class="title-session">Session : 2026-2027</h2>
        </div>

        <div class="sub-header">
            Following are the verified details against this <b>IDENTITY CUM LIBRARY CARD</b>
        </div>

        <hr class="divider">

        <!-- Student Data Section -->
        <div class="content">
            <table class="details-table">
                <tr>
                    <td class="label">Enrollment No</td>
                    <td class="value" id="enrollment">--</td>
                </tr>
                <tr>
                    <td class="label">Roll No</td>
                    <td class="value" id="roll">--</td>
                </tr>
                <tr>
                    <td class="label">Class</td>
                    <td class="value" id="class">--</td>
                </tr>
                <tr>
                    <td class="label">Student Name</td>
                    <td class="value" id="name">--</td>
                </tr>
                <tr>
                    <td class="label">Father Name</td>
                    <td class="value" id="father">--</td>
                </tr>
                <tr>
                    <td class="label">Mother Name</td>
                    <td class="value" id="mother">--</td>
                </tr>
                <tr>
                    <td class="label">Mobile No.</td>
                    <td class="value" id="mobile">--</td>
                </tr>
                <tr>
                    <td class="label">Father Mobile No.</td>
                    <td class="value" id="father_mobile">--</td>
                </tr>
                <tr>
                    <td class="label">Permanent Address</td>
                    <td class="value" id="p_address">--</td>
                </tr>
                <tr>
                    <td class="label">Correspondence Address</td>
                    <td class="value" id="c_address">--</td>
                </tr>
            </table>

            <!-- Photo & Signature Box -->
            <div class="media-box">
                <div class="photo-box" id="photo_container">
                    Student Photo
                </div>
                <div class="signature-box" id="sig_container">
                    Signature
                </div>
            </div>
        </div>

        <!-- Verified Footer -->
        <div class="verified-text">
            Verified
        </div>

        <hr class="divider">
    </div>

    <script>
        // Student Database Dictionary
        const studentDatabase = {
            "17153": {
                enrollment: "-12313",
                roll: "17153",
                class: "BSC PART II",
                name: "JATIN",
                father: "JAWINDER",
                mother: "RANI",
                mobile: "9817102946",
                father_mobile: "9817102946",
                p_address: "LOGHARH PINJORE",
                c_address: "LOGHARH PINJORE",
                photo: "", // Put image link here if available e.g., "photo.jpg"
                signature: "" // Put signature link here if available
            }
        };

        // Fetch roll number from URL parameter, default to 17153 if none specified
        const urlParams = new URLSearchParams(window.location.search);
        let rollNo = urlParams.get('roll');

        if (!rollNo || !studentDatabase[rollNo]) {
            rollNo = "17153";
        }

        const data = studentDatabase[rollNo];
        document.getElementById('enrollment').innerText = data.enrollment;
        document.getElementById('roll').innerText = data.roll;
        document.getElementById('class').innerText = data.class;
        document.getElementById('name').innerText = data.name;
        document.getElementById('father').innerText = data.father;
        document.getElementById('mother').innerText = data.mother;
        document.getElementById('mobile').innerText = data.mobile;
        document.getElementById('father_mobile').innerText = data.father_mobile;
        document.getElementById('p_address').innerText = data.p_address;
        document.getElementById('c_address').innerText = data.c_address;
        
        // Handle photo display
        if (data.photo) {
            document.getElementById('photo_container').innerHTML = `<img src="${data.photo}" alt="Student Photo">`;
        }
        
        // Handle signature display
        if (data.signature) {
            document.getElementById('sig_container').innerHTML = `<img src="${data.signature}" alt="Signature">`;
        }
    </script>
</body>
</html>
