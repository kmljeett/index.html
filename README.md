<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Verification - DAV College</title>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
        }

        .container {
            background-color: #ffffff;
            width: 750px;
            padding: 30px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            box-sizing: border-box;
        }

        /* Header Layout */
        .header {
            display: flex;
            align-items: center;
            justify-content: flex-start;
            margin-bottom: 10px;
        }

        .logo {
            width: 80px;
            height: auto;
            margin-right: 20px;
        }

        .title-container {
            text-align: center;
            flex-grow: 1;
        }

        .title-container h1 {
            color: #b31217;
            font-size: 22px;
            margin: 0;
            font-weight: bold;
            text-transform: uppercase;
        }

        .title-container h2 {
            color: #b31217;
            font-size: 18px;
            margin: 5px 0 0 0;
            font-weight: bold;
        }

        .sub-header {
            text-align: center;
            font-size: 12px;
            font-weight: bold;
            color: #1a2b4c;
            margin-top: 15px;
            margin-bottom: 10px;
        }

        .divider {
            border: 0;
            height: 1.5px;
            background-color: #1a2b4c;
            margin-bottom: 20px;
        }

        /* Main Content Layout */
        .content {
            display: flex;
            justify-content: space-between;
        }

        .details-table {
            width: 70%;
            border-collapse: collapse;
        }

        .details-table td {
            padding: 6px 0;
            font-size: 13px;
            vertical-align: top;
        }

        .details-table td.label {
            font-weight: bold;
            color: #333;
            width: 40%;
        }

        .details-table td.value {
            color: #111;
            width: 60%;
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
            height: 160px;
            border: 1px solid #333;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            background-color: #fff;
        }

        .photo-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .signature-box {
            width: 140px;
            height: 45px;
            border: 1px solid #333;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            background-color: #fff;
        }

        .signature-box img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }

        /* Footer Verified Status */
        .verified-text {
            text-align: center;
            color: #b31217;
            font-size: 24px;
            font-weight: bold;
            margin-top: 25px;
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Header Section -->
        <div class="header">
            <img src="https://via.placeholder.com/80x100?text=DAV+Logo" alt="DAVC Logo" class="logo">
            <div class="title-container">
                <h1>DAV COLLEGE, SECTOR 10, CHANDIGARH</h1>
                <h2>Session : 2026-2027</h2>
            </div>
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
                <div class="photo-box">
                    <img id="student_photo" src="https://via.placeholder.com/140x160?text=Photo" alt="Student Photo">
                </div>
                <div class="signature-box">
                    <img id="student_sig" src="https://via.placeholder.com/140x45?text=Signature" alt="Signature">
                </div>
            </div>
        </div>

        <!-- Verified Footer -->
        <div class="verified-text">
            Verified
        </div>

        <hr class="divider" style="margin-top: 15px;">
    </div>

    <script>
        // Updated Student Database Dictionary
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
                photo: "https://via.placeholder.com/140x160?text=Jatin", 
                signature: "https://via.placeholder.com/140x45?text=Signature" 
            },
            
            
        };

        // Extract Roll Number from URL query parameter (e.g. ?roll=17153)
        const urlParams = new URLSearchParams(window.location.search);
        const rollNo = urlParams.get('roll');

        if (rollNo && studentDatabase[rollNo]) {
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
            
            if (data.photo) document.getElementById('student_photo').src = data.photo;
            if (data.signature) document.getElementById('student_sig').src = data.signature;
        } else {
            document.querySelector('.container').innerHTML = "<h2 style='text-align:center; color:red; margin-top:50px;'>Student Not Found</h2>";
        }
    </script>
</body>
</html>
