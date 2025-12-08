<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>ASE BOOSE Documentation</title>

    <!-- Google Font -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">

    <style>
        body {
            margin: 0;
            font-family: "Inter", sans-serif;
            background: #f4f6f9;
            color: #222;
            line-height: 1.7;
        }

        header {
            background: #2a4ba8;
            color: white;
            padding: 40px 20px;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 42px;
            font-weight: 800;
        }

        header p {
            font-size: 18px;
            opacity: 0.9;
        }

        .container {
            width: 86%;
            margin: auto;
            padding: 30px 0;
        }

        section {
            background: white;
            padding: 30px;
            margin-bottom: 25px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
        }

        h2 {
            margin-top: 0;
            color: #2a4ba8;
            font-weight: 700;
        }

        pre, code {
            background: #1b1b1b;
            color: black;
            padding: 12px;
            border-radius: 8px;
            font-size: 15px;
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 12px;
        }

        table, th, td {
            border: 1px solid #d9d9d9;
        }

        th {
            background: #2a4ba8;
            color: white;
            padding: 10px;
            font-weight: 600;
        }

        td {
            padding: 10px;
            background: #fff;
        }

        footer {
            background: #1d1d1d;
            color: #ccc;
            text-align: center;
            padding: 30px 10px;
            margin-top: 40px;
        }

        a {
            color: #2a4ba8;
            font-weight: 600;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        .download-btn {
            display: inline-block;
            background: #2a4ba8;
            color: white;
            padding: 12px 20px;
            border-radius: 8px;
            margin-top: 10px;
            text-decoration: none;
            font-weight: bold;
        }

        .download-btn:hover {
            background: #1f3880;
        }
    </style>
</head>

<body>

<header>
    <h1>ASE BOOSE Documentation</h1>
    <p>Full Interpreter & Graphics Drawing System Documentation</p>
</header>

<div class="container">

    <!-- Overview -->
    <section>
        <h2>1. Overview</h2>
        <p>
            BOOSE is a lightweight graphical interpreter designed to convert simple text commands
            into visual output on a drawing canvas. It demonstrates:
        </p>
        <ul>
            <li>Command parsing</li>
            <li>OOP design principles</li>
            <li>Canvas rendering using <b>AppCanvas</b></li>
            <li>Command factories using <b>ICommandFactory</b></li>
            <li>Unit testing (MSTest)</li>
            <li>Extensible command structure</li>
        </ul>
    </section>

    <!-- Features -->
    <section>
        <h2>2. Features</h2>
        <ul>
            <li>Move cursor using <b>moveto</b></li>
            <li>Draw lines using <b>drawto</b></li>
            <li>Draw shapes — <b>circle</b> and <b>rect</b></li>
            <li>Set pen color with RGB values</li>
            <li>Reset canvas to default</li>
            <li>Enable/disable filled shapes</li>
            <li>XML Documentation Generated from C#</li>
        </ul>
    </section>

    <!-- How BOOSE Works -->
    <section>
        <h2>3. How BOOSE Works</h2>
        <p>BOOSE reads user input and converts it into command objects:</p>

<pre>
moveto 50,100
pen 255,0,0
circle 100
</pre>

        <p>The flow:</p>
        <ol>
            <li>User types text commands</li>
            <li><b>AppCommandFactory</b> parses and maps commands</li>
            <li>Commands update the <b>AppCanvas</b> drawing</li>
        </ol>
    </section>

    <!-- Commands Table -->
    <section>
        <h2>4. Commands Reference</h2>

        <table>
            <tr>
                <th>Command</th>
                <th>Format</th>
                <th>Description</th>
            </tr>
            <tr>
                <td>moveto</td>
                <td>moveto x,y</td>
                <td>Moves cursor to (x,y)</td>
            </tr>
            <tr>
                <td>drawto</td>
                <td>drawto x,y</td>
                <td>Draws line to (x,y)</td>
            </tr>
            <tr>
                <td>pen</td>
                <td>pen r,g,b</td>
                <td>Sets pen color using RGB</td>
            </tr>
            <tr>
                <td>circle</td>
                <td>circle radius</td>
                <td>Draws circle</td>
            </tr>
            <tr>
                <td>rect</td>
                <td>rect width,height</td>
                <td>Draws rectangle</td>
            </tr>
            <tr>
                <td>reset</td>
                <td>reset</td>
                <td>Clears canvas + resets pen and cursor</td>
            </tr>
            <tr>
                <td>fill</td>
                <td>fill on/off</td>
                <td>Enables/disables shape filling</td>
            </tr>
        </table>
    </section>

    <!-- Input Rules -->
    <section>
        <h2>5. Input Rules</h2>
        <ul>
            <li><b>Coordinates MUST be comma-separated</b></li>
        </ul>

<pre>
✔ moveto 100,150  
✘ moveto 100 150
</pre>

        <ul>
            <li>RGB values must be 0–255</li>
            <li>Commands are not case-sensitive</li>
        </ul>
    </section>

    <!-- Structure -->
    <section>
        <h2>6. Application Structure (Developers)</h2>

<pre>
myBOOSEapp/
│── AppCanvas.cs
│── AppCommandFactory.cs
│── MoveToCommand.cs
│── DrawToCommand.cs
│── SetColourCommand.cs
│── CircleCommand.cs
│── RectCommand.cs
│── WriteCommand.cs
│── Program.cs
</pre>
    </section>

    <!-- Example -->
    <section>
        <h2>7. Example Program</h2>

<pre>
moveto 100,150
pen 0,0,255
circle 150

pen 255,0,0
moveto 150,50
rect 150,100
</pre>

    </section>

    <!-- Reset -->
    <section>
        <h2>8. Reset Functionality</h2>

<pre>
public void Reset()
{
    penColor = Color.Black;
    Xpos = 0;
    Ypos = 0;
    Clear();
}
</pre>

    </section>

    <!-- Troubleshoot -->
    <section>
        <h2>9. Troubleshooting</h2>

        <table>
            <tr>
                <th>Issue</th>
                <th>Cause</th>
                <th>Solution</th>
            </tr>

            <tr>
                <td>Shapes not appearing</td>
                <td>Values out of canvas bounds</td>
                <td>Use valid dimensions</td>
            </tr>

            <tr>
                <td>Color not changing</td>
                <td>Invalid RGB</td>
                <td>Use 0–255</td>
            </tr>

            <tr>
                <td>Commands ignored</td>
                <td>Syntax wrong</td>
                <td>Use comma-separated format</td>
            </tr>

            <tr>
                <td>App crash</td>
                <td>Command not mapped</td>
                <td>Ensure factory includes the command</td>
            </tr>
        </table>
    </section>

    <!-- XML Documentation -->
    <section>
        <h2>10. XML Documentation</h2>

        <p>You can download or view XML documentation from this link:</p>

        <a class="download-btn" href="https://github.com/mdmohid/ASE_BOOSE_Documentation/tree/main/XML_Documentation">Download XML Documentation</a>

        <p>(Upload your XML file into your GitHub Pages repo)</p>
    </section>

    <!-- Author -->
    <section>
        <h2>11. Author</h2>
        <p><b>Name:</b> MD. Mohid Alam</p>
        <p><b>Project:</b> ASE BOOSE Interpreter Assignment</p>
        <p><b>Hosted Documentation:</b>
            <a href="https://mdmohid.github.io/ASE_BOOSE_Documentation/">https://mdmohid.github.io/ASE_BOOSE_Documentation/</a>
        </p>
    </section>

</div>

<footer>
    © 2025 BOOSE Application Documentation — All Rights Reserved.
</footer>

</body>
</html>
