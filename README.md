<!DOCTYPE html>
<html lang="en">
<!-- Keep your existing head and style sections the same -->

<body>
    <div class="container">
        <h2>Supply Request Form</h2>
        <p>Select items from our common supplies list or request custom items</p>
        
        <!-- Add this hidden iframe for the Google Form submission -->
        <iframe name="hidden_iframe" id="hidden_iframe" style="display:none;"></iframe>
        
        <!-- Update the form with your Google Form action URL -->
        <form id="supplyForm" action="YOUR_GOOGLE_FORM_URL" method="POST" target="hidden_iframe">
            <!-- Update input names to match Google Form field names -->
            <div class="form-group">
                <label for="entry.123456789">Your Name</label>
                <input type="text" id="entry.123456789" name="entry.123456789" required>
            </div>
            
            <div class="form-group">
                <label for="entry.987654321">Your Email</label>
                <input type="email" id="entry.987654321" name="entry.987654321" required>
            </div>
            
            <!-- Continue with other form fields, updating the entry.XXXXXX IDs -->
            
            <button type="submit">Submit Request</button>
        </form>
        <div id="successMessage" class="success-message">
            Request submitted successfully!
        </div>
    </div>

    <script>
        // Updated JavaScript for Google Form submission
        document.getElementById('supplyForm').addEventListener('submit', function(e) {
            var form = this;
            var successMessage = document.getElementById('successMessage');
            
            // Show success message
            setTimeout(function() {
                successMessage.style.display = 'block';
                form.reset();
                
                // Hide message after 5 seconds
                setTimeout(function() {
                    successMessage.style.display = 'none';
                }, 5000);
            }, 1000);
        });
    </script>
</body>
</html>
